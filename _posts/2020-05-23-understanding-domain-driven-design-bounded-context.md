---
published: false
layout: post
author: dinakaran
image: assets/images/ddd.gif
---

Domain Driven Design is the foundational pillar for any of the micro-services implementation. It helps to broadly classify the microservices. So think microservices, think domain driven design. Both gel well with each other. 

One of the challenges encountered with designing micro-services is identifying the main domains and sub-domains and forming boundaries around them. And this establishing of boundaries amongst microservices is usually referred to as Bounded Context.

## What is Domain Driven Design and what Domain ?

Domain Driven Design adopts the principle of designing software systems based by keeping domain as being the main focus. It is not necessarily a new concept that came along with microservices, but a concept well suited for microservices. These are the core business components of a system. For instance, in the case of an organization,  employees, departments and projects may be the core domain components. Processes and structures are placed around them.  

Bounded context is all about establishing the boundaries of business rules, processes and interactions between different domains. It helps to demarcate boundaries and ensure other systems respect these context. 

To give an example, let us take the example of an organisation. Employee, Appraisal and Payroll can be 3 different domain objects. There may be 100 different attributes that pertain to an employee like personal information, education and experience etc. All this information will be managed and stored within the Employee Domain using applications and systems developed to manage this information.

An Appraisal can be another domain for capturing and assessing the performance of an employee. Even though the name of the employee or employee id from Employee system may be used in the Appraisal system, other than the references, no other information about the employee like address and other non-relevant information for appraisal system will be viewed or updated through the Appraisal system. Similarly, in the employee system, no information about the employee's performance will be available.

The Payroll domain and supporting systems too would use the employee id or employee name,  but that is pretty about it. But this begs the question: Payroll system may need more information about the employee to display in the monthly payroll slips. How to fetch the employee's other information like tax number, date of joining or designation? This information is retrieved by calling the Employee system that may expose one of its services and getting back the required details. The payroll system cannot directly connect to the Employee database to fetch the information, but it would rather use one of the services exposed by the Employee system to fetch and update the information. 

 In essence, why domain driven design and bounded context required? It helps to form a ubiquitous language through which people within and outside their teams and organization can communicate easily. All of them will mean and refer to the same thing.  Employee System, Payroll System and Appraisal System help us to easily identify what each of the systems does and helps to easily understand the boundaries. 

## How to identity Domains and Bounded Contexts?

Let us say, we are in the process of building microservices and need to come up with the main domain objects and bounded contexts. How to go about it? 

There are some established processes that can be followed to identify domains and bounded contexts. As application developers or architects, even though we may have the requirements and are aware of the innate working of various systems and dependencies, it would always be prudent to bring along a set of domain experts. These are generally the business people with good knowledge of the core business, process and contexts. 

## Event Storming

Event Storming is one of the techniques followed to come up with the Domain Objects, Bounded context and how they interact with each other. It is essentially a brainstorming session. More detailed information regarding this is available [here](https://medium.com/nick-tune-tech-strategy-blog/modelling-bounded-contexts-with-the-bounded-context-design-canvas-a-workshop-recipe-1f123e592ab) and [here](https://www.capitalone.com/tech/software-engineering/event-storming-for-microservice-architecture/) :  

During Event Storming, another essential information that emerges are the business events. These are usually referred to as Domain Events as well. These events represent a certain business activity. For example, an employee's appraisal process have the following events : 

- Appraisal process not yet triggered by the HR 
- Employee has completed the self-evaluation
- Manager has reviewed and provided feedback and ratings
- Employee and Manager has completed a one-on-one discussion
- The appraisal process is completed


As a result of event storming, we get the main domain objects, corresponding events as well. These events may represent a change of state within the domain system or to other systems as well. For example, once the appraisal process is completed only, the increase in pay for that year is computed and included as part of payroll for that employee. So in the context of microservices, it is very important to determine these business events and the corresponding change in state is propagated to other systems accordingly.   

## Decomposition Strategies

- Bounded Context
- Sub-Domains
- Business Process and Entities

More information [here](https://cdn.oreillystatic.com/en/assets/1/event/305/On%20microservices%2C%20bounded%20contexts%2C%20and%20everything%20in%20between%20Presentation.pdf) 

To know more about this, I have linked more articles on the same topic 

[https://www.slideshare.net/Pivotal/ddd-and-microservices-like-peanut-butter-and-jelly-matt-stine](https://www.slideshare.net/Pivotal/ddd-and-microservices-like-peanut-butter-and-jelly-matt-stine)

[https://debezium.io/blog/2020/02/10/event-sourcing-vs-cdc/](https://debezium.io/blog/2020/02/10/event-sourcing-vs-cdc/)







