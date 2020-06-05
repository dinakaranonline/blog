---
published: false
---
When it comes to microservices, the thinking around databases has to be radical and very different. Following are the essential considerations : 

### 1. No shared database among microservices 

Every microservice needs to have its own database and no two microservices can use the same databases to update or query data. The primary way of accessing other services to fetch or update data must be via an API. 

### 2.Embracing Polyglot Persistence

One of the main advantages of microservice architecture is that, based on the requirement, the choice of a database can be picked up. So there is no real constraint over choosing the same databases across different microservices. Based on the use case, the choice of database can be a good old relational database or NoSql or Document or Graph Database. 

### 3.Eventual Consistency where ever possible

As microservices tend to be distributed with quite a few network hops, eventual consistency can be embraced wherever possible. It particularly works well in asynchronous scenarios. It will also lead to better performance and reduced latency with the innate ability to be fault-tolerant. 

### 4.Being comfortable with no single source of truth and data denormalization  

In a conventional way of thinking, data has to have a single source of truth and data cannot and should not be duplicated. However, in microservices, some amount of data deduplication and denormalization cannot be avoided. While this is not the default recommendation, in situations where some amount of data deduplication may be required to avoid round trips or reduce latency through network hops, it is an acceptable approach,  but the synching of data between different systems must be thought through so that the data is always up-to-date. 

### 5.Scaling databases to match application scaling

Scaling of databases is not quite efficient yet in the same way innovations have happened in the scaling of the application. While applications are elastic and can scale up and down based on the need, databases cannot respond to the same extent in terms of scaling up and down. For example, the database connection pooling and time out would be a persistent constraint in the database side of things. In most scenarios, the scaling capabilities are limited by the database constraint. However of late, databases have been re-architected to take advantage of the cloud and the infrastructure heft that it provides. Even SQL databases have horizontal scaling capabilities with multi-master writes and dozens of read replicas for better performance and availability.      

While I have just touched the surface in terms of factors that can impact the choice of databases in a microservice world, a thoughtful approach must be followed in final decision with a good view of the kind of advantages, challenges and trade-offs each of these databases offers.