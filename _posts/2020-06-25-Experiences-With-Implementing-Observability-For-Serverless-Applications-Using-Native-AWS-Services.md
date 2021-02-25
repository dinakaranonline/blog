---
title: Experiences With Implementing Observability For Serverless Applications Using
  Native Aws Services
date: 2020-06-25 00:00:00 Z
categories:
- Programming
layout: post
author: dinakaran
image: assets/images/observability.jpg
---

In case of the traditional setup of cloud infrastructure, logging and monitoring is quite a huge architecture decision - be it deciding on the logging and monitoring stack of ELK vs EFK and setting up all required infrastructure to collect logs and tools and dashboard to be set up. For anyone starting in the Cloud, it could be a daunting task. There needs close interaction between Application and Infrastructure teams to get all of this coordinated and setup. When it comes to Observability, there are a lot of 3rd party tools widely marketed and recommended.

But in my experience, we were able to take up most of the observability requirements with the Native AWS services itself. In this article, I will share my experiences on how we set up and implemented observability for various use-cases and the various AWS services to manage each of the different requirement.

At the outset, these may not look like an ideal setup for observability. But then, context becomes very essential. The setup and management of the  Serverless API backend with the combination of API Gateway, Lambda, Dynamo DB, SNS, SQS and Aurora etc was purely set up and run by Developers of the product team with little to no help from Infrastructure/Operations team.  

All these various monitoring alerts were set up and managed by Developers who have a good sense of Application Knowledge and can make thoughtful decisions over the right kind of logging and monitoring. In fact, even before customers reporting any issues with the service, the SNS error notifications would start appearing in the monitoring inbox and we are always one step ahead in terms of dealing with various error conditions. 

The AWS tools used for this are 
- Cloud Watch Logs
- Cloud Watch Metrics
- Cloud Watch Alarms
- X-Ray
- SNS


### 1.Using Cloud Watch Logs and Apache Logging Filter to dynamically enable debug logging 

We have integrated a lot of 3rd party API in our application and  there are cases where few requests fail and when we reach to the team responsible for maintaining the service, the team insist on sharing the entire API request of the failure request 

In this specific instance, since the 3rd party was a SAAS provider and was relatively big company supporting many applications in various geographies, they have sent up a ticketing system to raise a request with relevant details. 

Since logging every single request could mean too much overhead and increase in associated costs, we have not enabled detailed logging by default. And we also wanted a solution that could be helpful not for this 3rd party service, but for other external services as well. So what we required was a way to enable the logging to debug level for  a small period of time if required and then switch it back to lightweight logging. And since the issue could very arise in case of other 3 party services too,  we thought of a common solution that could be very effective. 

So we came up with a way to enable logging at the API level .  We were using Apache HTTP Client for API invocation to external API's. Apace HTTP client provides a logging filter that helps to monitor every request invoked through  Apache Client with detailed information of request URL, HTTP methods,  request and response body along with detailed header information.

 With this setup, by default, the logging level is INFO and only essential logging is made available. But once we encounter errors and SNS notifications are triggered, we enable the logging to debug mode for that specific lambda through environment variable for a short period of time. 

Once debugging is enabled, the detailed request/response for all the API invocation that happens in the lambda will be logged in CloudWatch Logs. And this gives complete visibility to the API request and response details. Apache Logging filter does a fabulous job of capturing the request in its entirety in Cloud Watch Logs.  

Once the logs are dumped in Cloud Watch Logs , we fetch these logs and then send to 3rd party for further investigation. Since debug level logging is costly, we came up with this nifty approach of enabling logging dynamically using environment variables for that specific lambda and get the required logs for analysis and then decide on the next course of action.   

This same approach could be used for all external services available already and can be implemented in future. This helped us to reduce our time to debug and resolve the issue to a great extent. 

### 2. Leveraging Cloud Watch Logs, Metrics and Alarms for targetted monitoring 

To ensure users do not misuse the authentication system, we set up alerts where-in if the authentication failure happened very frequently and crosses a threshold in a given time interval, Cloud Watch Alarms would start sending notification to the teams using SNS for further action. 

The whole process can be roughly dividing into 3 different steps 

**1. Decide on the error message to be monitored in Cloud Watch** 

For a given error condition, we decide on the error message that will be logged in Cloud Watch Logs. And this error message needs to be monitored by Cloud Watch Metrics. So every time there is an incorrect authentication, this error message is dumped in the console. There is no use of sending SNS notification for every single case because there may be genuine failure scenarios and no actions required on those scenarios. 

**2. Define the Cloud Watch Metrics**

Next step is to define Cloud Watch Metrics to monitor this error message. Metrics on how many similar error messages were dumped in Cloud Watch Logs will be captured as part of these metrics. Once this is set up, the Cloud Watch Metrics give good metrics information on the occurrence and frequency.

**3. Define Cloud Watch Alarms and SNS error notification**

The final step is to create Cloud Watch Alarms which is mapped to the Cloud Watch Metrics. When a given set of Cloud Watch Metrics is reached, for example: If the login failures are crossing more than 100 within 30 minutes or so, Cloud Watch Alarm will be triggered and the alarm will trigger a notification to users or group of users through  SNS notification. This way there is more granularity and control available to make thoughtful monitoring rather than dumping too much SNS notifications flooding inbox that no one takes care of seriously. 

### 3.Searching through Cloud Watch Logs using SQL like queries 

Cloud Watch Logs has a newer interface built into it and provides more powerful ways to search/query for logs using SQL kind of queries and responses was super fast enough to fetch the required details.

Our query was to search for a certain error message for a given time period with the most recent occurrence at the top with some kind of limiting conditions. The query was very natural for developers who are used to writing SQL queries and we were able to fetch information very swiftly.  

### 4.Distributed logging for Lambda based MicroServices with API Gateway Request ID 

We had implemented Lambda using a microservices-based approach where one lambda can invoke another API which triggers another lambda. And with this kind of situation, debugging through Cloud Watch Logs could be painful. So the recommended approach is to append the API Gateway request id as part of header context information that can be retrieved by all lambdas. So by attaching an API Gateway request-id, all the different lambdas that were part of a single request could dump the same request-id in Cloud Watch Logs and this way, it was easier to trace the requests across different lambdas.

What needs to be understood is that there is no need for a comprehensive setup to get this feature. All that was required was to turn on few configurations at API Gateway and add necessary logging so that a lightweight distributed tracing could be easily enabled. Although this setup was not exhaustive and we still had to look for logs in different lambdas, searching with the same request-id helped to a great extent.  

### 5. Tracing request/response latency using X-Ray

As remarked earlier, our application used a lot of different 3rd party API. Some of them had latency issues intermittently with few requests timing out after more than 30 seconds. So we went ahead with implementing X-Ray for all interactions - be it within the internal services, with AWS services and as well as external API's. So once this was set up, it was very easy to look at the intermittent failures by looking at X-Ray.

Through X-Ray, we were able to neatly trace the request and response time it takes at each layer from the time code execution starts and time taken to connect and execute various operations like reading or writing to   DynamoDB or Aurora or fetching or posting data into 3rd party services. It is easy to find metrics on how many requests were served in a  given point of time, the accompanying HTTP error codes and the total time taken to complete the request. Out of say 100 requests, we could easily figure out that 10 % of request that resulted in latency issues and we were able to share the detailed tracing data for course correcctions. 

X-Ray is an excellent tool for tracing


### 6. Monitoring setup using AWS SNS for email trigger notifications 

What we have realized is that monitoring in the cloud-native world is not about building a dashboard that needs to be watched continuously with a lot of green and red boxes. Rather the monitoring can be reactive and action can be taken only when the notifications reach our mailboxes. Any available default dashboard are good enough to understand the state of the various lambdas, API Gateway and API requests. Beyond that, there is no need for dedicated monitoring where someone watches a dashboard 24X7. 

_Here are the various ways we have set up various monitoring alerts._

1. Set up email alerts for any critical exceptions where lambda pushes messages to SNS topic and subscribers to the topic will receive notifications. In our case, we have configured it to be delivered via email.One interesting situation where it helped was that the clientside validation was bypassed and requests failed in server-side API and we started receiving notification. Users did not report this issue too.  And once we started receiving the alerts, we examined the request body sent as part of the request and we were puzzled how the scenario happened because it could not be replicated in the front end.  The field would not accept any non-numbers and UI validation took care of it. But then after breaking our heads for couple of hours, we could figure out how this is happening. Then we realized that users were copy-pasting the non-number values and for this sceanrio, the UI validation was not handled and it let non-numbers be sent as part of this request. The monitoring alerts setup helped to a great extent to resolve issues and make the product more refined and user experience better even if users did not complain about the issues. Since the developers were in charge of monitoring these alerts, issues reported this way were immediately added to the product backlog and prioritized as part of future sprints. 

2. We have setup Cloud Watch Events for external 3rd party API  authentication tokens that refreshes once in 24 hours/90 mins and stored in DynamoDB and used by the application. If this cloud watch event failed due to credentials rotation, but not informed to the other teams, we get immediate alerts in our inbox and swift resolution of reaching out to the external team would be taken up. There were times when the SSL certificate expires and not renewed by the external API's , and for all these situations, the SNS monitoring would help to understand what is happening and help to take necessary action immediately even before users report any issues.
 

Overall from our experience, we found the native Observability Tools slowing evolving to make the process of managing and running applications simpler and easier. Also, there is a change in mindset happening , where developers who are used to building products and not very concerned about supporting the applications since there is always a different team managing it, is giving way to developers walking down the aisle to the other side to learn and understand Observability and get metrics on how well their code is performing giving them a better perspective to efficiently build applications and improve the quality of the code and thereby the product they are building.

One recurring pattern that I have noticed is that, there is no one size fits all approach . Companies with the scale of Google or Uber may have different kind of site reliability and monitoring setup  whereas smaller companies/ applications may have a different requirement. Also the Conway's Law may come in the way of trying to replicate best practices from elsewhere. The whole aspect of observability and monitoring requirements may evolve over a period of time and may get even simpler , but trying to replicating patterns and practices from other companies without understanding the context and architecture decisions behind such a setup may result in over engineering if not carefully considered. While it is necessary to keep eyes on the floor to understand how the market and industry is evolving, it is important to only do what is required and necessary with some restraint would help us to manage and run applications better without getting overwhelmed.
