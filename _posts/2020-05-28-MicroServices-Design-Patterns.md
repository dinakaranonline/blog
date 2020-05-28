---
published: true
layout: post
author: dinakaran
image: assets/images/Design-Patterns.jpg
---
One look at the various microservices patterns and the sheer amount of patterns would look daunting for anyone starting new. Design patterns for microservices can be broadly classified around 4-5 categories and with each category having 3- 5 patterns. A more detailed look at each of the patterns is available here. 

**References**: [https://dzone.com/articles/design-patterns-for-microservice](https://dzone.com/articles/design-patterns-for-microservice)s

Here is a brief overview of the various patterns.

### Decomposition Patterns

- **Decomposition by Business Capabilities** - Build service based on business capabilities

- **Decomposition by Sub- Domains** - Domain-Driven Design and Bounded Context with clear boundaries

- **Strangler Patterns** - A Section of the monolith pointing to a new microservice while rest being served by a monolith. And the giant monolith will be decomposed into smaller microservices,  one functionality or component at a time

### Integration Patterns

- **API Gateway pattern**
	Can be used by different clients. Backend For Front End ( BFF),
 	Useful for aggregation /data  manipulation
 	Handle different type of protocol. XML/ JSON transformation etc
    
- **Aggregator Pattern**- Fetch, aggregate and transform data from different back end services endpoints. Can be done via API Gateway pattern or Composite Microservice pattern

- **Client-Side UI Composition Pattern** - Each section in a page of the front end application will call separate back end services to consume data

### Database Patterns

- **Database per Service** - One database per microservice

- **Shared Database per Service** - For existing brownfield applications with no option to go for database per service

- **Command Query Responsibility Segregation Pattern ( CQRS)** - Create/Update / Delete done using commands and fetching of data using queries. Query fetches data from multiple microservices using materialized views

- **SAGA patterns** - Business process defined with compensating actions for failed transactions

### Observability Patterns

- **Log Aggregation** - Eg. Cloud Watch

- **Performance Metrics** - Monitor the application performance
	-	Push - New Relic, App Dynamics
	-	Pull - Prometheus

- **Distributed Tracing** - Trace request between microservices Eg. X-Ray. Spring Cloud Sleuth

- **Health Check** - Check the status of each server or container by sending heart beats

### Cross-Cutting Concern Patterns

- **External Configuration** - Retrieve environment variables, configuration from version controlled system . Eg. Spring Cloud Server

- **Service Discovery Pattern** - Fetch metadata of all services hosted. Eg. AWS ELB, Netflix Eureka

- **Circuit Breaker Pattern** - When microservices downstream are not available, disconnect from back end service as safe fail over switch and return error messages instead of flooding the request

- **Blue-Green Deployment** - Two identical environments running in parallel in production. Green is the existing one, Blue is the new one. Once Blue environment is validated, route requests to these resources and switch off Green environment.

### Pub-Sub Patterns

Publisher - Subscriber Pattern is widely used in the event-driven asynchronous architecture. When a certain event has occurred, a message is published to the message queue. And subscribers are waiting to read messages from the queue based on the events. This is one of the widely used patterns that provides a lot of loose coupling and has options to retry for failures and take necessary actions.


Few more: Sidecar, Chained Microservice, Branch Microservice, Event Sourcing Pattern, Continuous Delivery Patterns
Another write up of similar and few more patterns identified here. 
[https://medium.com/@madhukaudantha/microservice-architecture-and-design-patterns-for-microservices-e0e5013fd58a](https://medium.com/@madhukaudantha/microservice-architecture-and-design-patterns-for-microservices-e0e5013fd58a)

## Products/services that address these design patterns

Many of the patterns listed here are now being offered as a feature or product by cloud providers and other vendors. Depending on what type of technology stack that is being considered, some of the features may come out of the box and reinventing the wheel is not required. 

Netflix in their initial days of moving to microservices built many of these components from scratch. Nowadays these components are available as managed services. Instead of getting overwhelmed with the multitude of design patterns and implementation, if the use case and context matches, pick one of existing products or services. It is not required to build everything from scratch.
