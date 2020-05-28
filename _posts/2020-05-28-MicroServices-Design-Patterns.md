---
published: false
---
## Microservices Design Patterns

One look at the various microservices patterns and the sheer amount of patterns would look daunting for anyone starting new. Design patterns for microservices can be broadly classified around 4-5 categories and with each category having 3- 5 patterns. A more detailed look at each of the patterns is available here. 

**References**: https://dzone.com/articles/design-patterns-for-microservices

Here is a brief overview of the various patterns.

### Decomposition Patterns
- **Decomposition by Business Capabilities** - build service based on business capabilities
- **Decomposition by Sub- Domains** - Domain-Driven Design and Bounded Context with clear boundaries
- **Strangler Patterns** - a section of the monolith pointing to a new microservice while rest being served by a monolith. And the giant monolith will be decomposed into smaller microservices,  one functionality or component at a time

### Integration Patterns
- **API Gateway pattern**
	 can be used by different clients. Backend For Front End ( BFF),
 	Useful for aggregation /data  manipulation
 	handle different type of protocol. XML/ JSON transformation etc
- **Aggregator Pattern**- fetch, aggregate and transform data from different back end services endpoints. Can be done via API Gateway pattern or Composite Microservice pattern
- **Client-Side UI Composition Pattern** - each section in a page of the front end application will call separate back end services to consume data

### Database Patterns
- **Database per Service** - one database per microservice
- **Shared Database per Service** - for existing brownfield applications with no option to go for database per service
- **Command Query Responsibility Segregation Pattern ( CQRS)** - Create/Update / Delete done using commands and fetching of data using queries. Query fetches data from multiple microservices using materialized views
- **SAGA patterns** - a business process defined with compensating actions for failed transactions
- 		Choreography
- 		Orchestration

### Observability Patterns
- **Log Aggregation** - Eg. Cloud Watch
- **Performance Metrics** - how well the application is performing
-	 	 Push - New Relic, App Dynamics
-		 Pull - Prometheus
- **Distributed Tracing** - trace request between microservices Eg. X-Ray. Spring Cloud Sleuth
- **Health Check** - check the status of each server or container

### Cross-Cutting Concern Patterns
- **External Configuration** - to pick environment variables, configuration from version controlled system . Eg. Spring Cloud Server
- **Service Discovery Pattern** - find metadata of all services hosted. Eg. AWS ELB, Netflix Eureka
- **Circuit Breaker Pattern** - when microservices downstream not available, disconnect from back end service and return errors instead of flooding the request
- **Blue-Green Deployment** - Two identical environments in prod running parallel. Green is the existing one, Blue is the new one. Once Blue is validated, route requests to these resources and switch off Green.

### Pub-Sub Patterns
Publisher - Subscriber Pattern is widely used in the event-driven asynchronous architecture. When a certain event has occurred, a message is published to the message queue. And subscribers are waiting to read messages from the queue based on the events. This is one of the widely used patterns that provides a lot of loose coupling and has options to retry for failures and take necessary actions.


Few more: Sidecar, Chained Microservice, Branch Microservice, Event Sourcing Pattern, Continuous Delivery Patterns
Another write up of similar and few more patterns identified here. 
https://medium.com/@madhukaudantha/microservice-architecture-and-design-patterns-for-microservices-e0e5013fd58a

## How products/services address these design patterns?

Many of the patterns listed here are now being offered as a feature or product by cloud providers and other vendors. Depending on what type of technology stack that is being considered, some of the features may come out of the box and reinventing the wheel is not required. 

Netflix in their initial days of moving to microservices built many of these components from scratch. Nowadays these components are available as managed services. Instead of getting overwhelmed with the multitude of design patterns and implementation, if the use case and context matches, pick one of existing products or services. It is not required to build everything from scratch.

