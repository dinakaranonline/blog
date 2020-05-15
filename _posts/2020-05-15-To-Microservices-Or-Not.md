---
layout: post
title: To Micoservices or not
author: dinakaran
image: assets/images/switch_to_microservices.jpg
published: true
---

The decision of whether to go for microservices or stick to a monolith is a constantly recurring question. The simple answer is, it depends on the context. Having said that, it would be good to comprehend the major factors that would impact our decisions. 

### Case of Microservices for Green Field applications

It is recommended to design with a [modular monolith](https://www.infoq.com/news/2020/05/monolith-decomposition-newman/) ( [explained here](https://medium.com/design-and-tech-co/modular-monoliths-a-gateway-to-microservices-946f2cbdf382) ) design pattern and then if required, branch off easily into separate microservices later if the situation demands. As part of building the modular monolith, set up  DevOps CI-CD pipeline stuff with Infra As Code automation so that the move to microservices will be slightly less painful.

So in principle , if the need for microservices is not clearly understood and if the team building has no prior experience and there is no business case to do so , it is better to stick to a modular monolith. And then the situation would presents itselves in the future magically prompting us to think in the direction of microservices. 

### Case of Microservices for existing monolith applications 

**Prerequisite**: DevOps CI-CD pipeline is already available

Use modular monolith design to re-architect existing applications as part of  development. Understand the pain points of having a monolith and what problems can be exactly solved when going for microservices and how microservices will help to solve them. An outcome-based thoughtful consideration is required here.

Some major points to consider

### Factors favouring Microservices :

- Microservices gives scaling and slasticity consideration. But that is not only the main reason for going to microservices. Ability to deploy code independently is another main reason. 

- Small independent teams can be formed around Microservices. More developers can start working just by understanding boundaries and how services interact with each other. 
 
- Risks are minimized and isolated. The blast radius is small when something goes wrong as impacts are contained within the microservices when compared with a monolith.
 
- Not restricted to a tech stack. Teams can change tech stack based on their choice, preference and requirements. It should be easier to choose to move from MySQL to NoSQL if the situation demands. 

- CI-CD process is faster as microservices will deploy fewer components, runs tests for fewer components. In the case of large monoliths, this is not entirely true and in some cases, full deployment takes around 30-40 mins without running tests. 
  
- Microservices can be independently and infinitely scaled, if microservices are stateless and uses only externally managed services for data.  

- Once the development toolkit is established and proper boundaries defined, CI-CD pipeline is set up properly, feature development and velocity can be increased. 
 
- Release planning for each feature can be done at the microservice level. No constraints on releasing code and no need for a large release planning and coordination.


  

### Factors Against Microservices : 


- The added complexity in terms of infra and cost, leads to the case of over-engineering in many instances. Need to think deeply and take balanced educated decisions.
 
- DevOps automation done for monolith is a good starting point. If there is no DevOps automation, stay away from microservices.
 
- Need for an orchestration and aggregation layer which is essentially a light weight monolith for a few use cases , meaning monolith cannot be avoided completely.  

- Security across microservices is additional work and needs to be well thought through. 
 
- De-normalizing data and creating siloed copies into multiple systems to avoid latency of calling other microservices to fetch required information. 
 
-  Knowledge of the build and deployment process is complex with a host of different options to choose from. The decision on whether to go the IAAS route or PASS with containers or FAAS route needs detailed evaluation . All of them come with their own set of quirks and complexities.   
 
- Concept of bounded context, if not understood well, can become a challenge to manage over a period of time if not kept in check. 
 
- Unit testing can be more complicated as we need to mock all internal microservices as well and handle exception scenarios for each of them.  
 
- Microservices with too many hoops, one microservices calling another , which in turns calls another  for synchronous requests can be quite challenging as latency will increase. Microservices works well for asynchronous requests with eventual consistency. The common available microservices patterns need to be fully understood and unless a clear understanding of the patterns to be used for various use cases is available, the implementation would lead to unnecessary complexities.  
 
- Microservices seamlessly blurs boundaries between Infrastructure, Application and DevOps.  Application Developers generally are not very well versed with concepts of containers, docker files and container orchestration strategies. DevOps are not very well versed with Application, System Design and related architecture while system admins are generally used to provisioning and managing servers ,network , security and other configuration. Engineers with all these 3 combined skill sets are required to have an end-to-end view and marshall people within the team accordingly.  
 
- Logging, Tracing and Debugging can introduce additional layers of complexity and it will be very difficult to debug microservices and trace back the root cause. An efficient Observability mechanism needs to be put in place to understand how well the system is performing and to deal with any issues arising out of it and this again takes quite some time to setup over a long period of time.   
 
- Committing a transaction and rollbacks can be quite difficult. In the case of a monolith, it is easier to group related actions and data into a transaction and then roll back if one of them fails. But in case of microservices, roll back approaches need to thought of, in case if one of the services is failing temporarily. 

- Buidling microservices without adopting PAAS or CAAS or FAAS solutions would lead to the full-fledged implementation of required components of microservices following the Netflix Spring Cloud architecture . All of these will result in more complexity.

So to conclude , Microservices as an option should not be tried just because it is the new shiny toy in town. Generally speaking, case for microservices would present itself when trying address the challenges of managing a complex monolith application. Only and only when the business case presents itself, the decision to go towards micro services should even be considered. It will be a wise move to make changes incrementally to a monolith application by tearing away small features from monolith and building it as a microservices. This will help to un-cover the scenarios and challenges and ways to address them before jumping into the bandwagon in entirety. 


Following are some of the products, toolsets, approaches that be can be considered 

- **Cloud** -  IAAS ,  PAAS or FAAS   
- **DevOps**  - CI/CD using Jenkins or equivalent, Terraform , Ansible 
- **Microservices** Development - Bounded Context, Stateless vs Stateful, Aggregates, Data duplication, Transaction management, microservices design pattern


### For Additional Reading :

-Domain Driven Design
-Aggregates in context of Domain Driven Design 
-Microservices Design Patterns
-Microservices - IAAS , PAAS or FAAS
-Microservices and Security
-Microservices and Transactions
-Microservices and Stateless vs Stateful Consideration


I will try to cover some of the concepts listed above in the upcoming posts shortly. 

