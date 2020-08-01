---
published: true
layout: post
author: dinakaran
image: assets/images/slowinternet.jpg
categories:
  - Programming
---

AWS and Cloud is all the rage these days and almost everyone is jumping into the bandwagon. But to get started in AWS may feel very daunting because AWS has so many different services and offerings. Depending on your current skill set, it may be very difficult to understand where to get started, especially when one wants to self-learn. 

When I started to explore AWS in 2018, this is exactly how I felt. The whole world of AWS felt very vague and confusing to me coming from an application development background. AWS and their services are currently targetted around 4-5 different kind of skillset. To build solutions in AWS, one may have to end up knowing many of these services at least at a  high level. AWS certification path gives good insights on how we can approach AWS.
 
**AWS Practitioner** - For professionals not necessary from the tech-heavy roles, but wanting to get a hold on what AWS is all about.  

**AWS Solution Architect** - Infrastructure Heavy. Typically centred around the migration of existing applications and workloads from On-Premises to the Cloud, managing infrastructure in AWS. Essentially the Infrastructure-As-A-Service paradigm. 

**AWS System Administrators** - Infrastructure and Operations heavy. Management and monitoring of Servers, Services, backups etc.

**AWS DevOps** - Setting up of CI-CD pipeline using AWS CI-CD tools like AWS Code Commit, AWS Code Build, AWS Code Deploy and Infrastructure As Code ( IAC) using Cloud Formation, SAM and CDK     

**AWS Developers** - Primarily for Developers looking to build cloud-native applications

**AWS Big Data/IOT** - As the name implies, this has tools for people looking to build solutions on top of Big Data/IoT. The reason I club both Big Data and IoT is that for most of the Big Data use-cases, the data ingestion happens through IoT devices pre-dominantly. So both Big Data and IoT could go hand-in-hand with each other.

**AWS Machine Learning** - For Machine Learning use-cases using Sage Maker.

Now with this classification out of the way, for Application Solution Architects and Back End Developers wanting to start with AWS, following are the sequence of topics from AWS I would suggest to start with.

**1. AWS Basics**

A real high-level explainer on what AWS and Cloud Computing is all about. This will give a good overview of various services etc, a AWS Practitioner level knowledge. I would suggest not to spend more than a couple of hours on this.

**2. AWS Serverless Stack of Lambda, API Gateway, DynamoDB and S3**

With the basics out of the way, the starting point for Developers and Application Architects would be the paradigm of Functions As A Service ( FAAS). AWS Lambda is a good starting point. One can easily write lambda functions and test it  directly in browser console for a few languages like Node and Python. So to get started quickly with some dirtying of code, AWS Lambda is the best way to start.

Next step is to try researching more on the different use-cases that AWS Lambda can solve and with that, the idea of Serverless should begin to emerge. Lambda in combination with API Gateway, DynamoDB, S3 and other loosely grouped services are referred to as the Serverless stack. Most of these services come under the free tier with some limits and hence can be used for self-learning

**3. AWS Managed Services of Queues, Pub-Sub mechanisms, cron jobs and relational databases RDS**

Once the basic use-cases provide a good insight into the capabilities of Serverless stack, the next pit stop could be trying to understand the different kind of orchestrations that are possible. AWS Simple Notification Service( SNS ), AWS Simple Queue Service ( SQS ) and AWS Simple Email Service ( SES) can help with a wide variety of use-cases and help you to better appreciate event-driven architectures. Cloud Watch Events provide cron job kind of capabilities as well. All of these services are pay-as-you-use and most of them come within the free tier.

AWS also provides Relational Database Service like MySql, Postgresql etc. But all of these are not free and they run 24*7. To get a taste of RDS, I would suggest to try out Aurora MySQL/Postgresql Serverless which has pay based on usage level. There are limitations on the service, but good for exploring the relational database use-cases. 

**4. AWS DevOps**

Once enough amount of serverless and managed services are explored, the next would be to set up CI-CD process. Again most of these tools are pay per use and has free tier options. AWS Code Commit --> AWS CodeBuild --> AWS CodePipeline should help with the CI-CD process. Again all one has to write is a few lines of code in YAML configuration. 

One distinct new concept one may learn here is the Infrastructure-As-Code ( IAC). A typical CI-CD process is always about building, packaging and deploying code into existing servers. But with the possibility of On-Demand provisioning of AWS resources, tools like Cloud Formation, Cloud Development Kit CDK and SAM could help with integrating the creation of resources into the CI-CD pipeline. This could be really daunting. But countless examples online could help us navigate this slightly complex YAML configuration files. If Cloud Formation and YAML feel complicated, check out CDK where the automation of resources could be done in languages developers are already aware. This option is relatively new and not widely adopted though. 

**5. Microservices using AWS Elastic Container Services ECS & Fargate**

Most of the general recommendation for Developers would be to start with microservices on the cloud and this should have been the first suggestion. But what I found is that the serverless stack of API Gateway and Lambda offer a lot of a better abstraction and easier, to begin with. With Microservices, you probably need containers which would mean knowledge of Docker and container orchestration services like ECS or Fargate.

Stay away from Kubernetes unless otherwise, your project needs it. Read the fundamentals maybe, but I found it to be way too complex. I personally feel that Kubernetes is not for Developers and mostly for Infrastructure and Operations. 

Once you get accustomed to these main focus areas, you may get a reasonable idea of AWS and the endless possibilities. It is not just AWS, even Google and Azure provides similar services and you can try them. Based on your interests, you can explore other services depending on your interest. There are countless of tutorials available online, especially on Youtube.

For people from a programming background, AWS may feel a little bit intimidating at the start. But as you start exploring more ( it takes a bit of time), you slowly understand the power of cloud computing and why the industry is shifting to it significantly. 

**The Mind Shift On Moving To Cloud**

One remarkable mind shift that is required with movement to Cloud is that a combination of different skill sets is required to do the same job. As Developers, we may be responsible for setting up and integrating CI-CD pipeline because it is relatively easier. Also, we may get exposed to the idea of Capacity planning for the applications we build and how much each of the services may cost. Previously we have may no clue on how much the servers cost. But now , it is very easy to view the cost incurred monthly and use that as a basis for future design considerations. All of these may feel a burden initially, but as we get used to the idea of building applications in the cloud, we would appreciate the power that each Developer has at their disposal to build applications with little to no help and deploy to production easily.
