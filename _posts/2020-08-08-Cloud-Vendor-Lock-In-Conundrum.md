---
published: false
---
The whole world and its infrastructure are moving into Cloud at a rapid pace in the last decade. Speed and frenzy of this transformation have caught everyone by surprise. From small start-ups to large organizations and government institutions, all of them are migrating their existing on-prem infrastructure into the cloud and building new-age solutions purely in cloud. 

### Building Innovations on the open standards

The fundamental ethos of software engineering has always been avoiding any vendor lock-in and to follow open standards as much as possible so that we are not tied to a company/vendor and be at their mercy. When it comes to programming languages and usage of open-source software, the whole software development community is now swiftly marching towards this. With Javascript and Typescript along with Angular, React and React Native, the front end ecosystem has largely remained open and the pace of innovation is astounding. Microsoft and Google aligning towards Typescript for Angular 2.0 was a significant shift in the way how even large organizations view open source. They are active contributors and also want to leverage the ecosystem that helps them build innovation faster. Same is the case with backend. Java is nowadays less preferred due to Oracle's trying to milk more money and people are gravitating towards more open source stuff with Python, Node, Go and other programming languages. Even from the database perspective, Postgresql is emerging as the de-facto standard along with MySql in the relational world, MongoDB / Cassandra etc as well in the No-SQL world. All of this resulted in truly championing the idea of open source and driving innovations on top of them. One significant outlier in this trend in the mobile app ecosystem where Apple and Google dictate the way around how apps have to be built, some of them are necessary to ensure privacy, security, but at other times, it is just to have control over the ecosystem. 

### Skirmishes between Public Cloud Providers and Open Source

And then the cloud happened. Whatever open-source innovations that are being built needs infrastructure and hosting and that resulted in public cloud providers coming up with new and interesting products that are helping fuel interesting awesome ideas. But with the pace of innovation by the big public cloud vendors who continue to incrementally roll out new products and updates, it becomes challenging to take a pause, reflect and think of open standards, vendor lock-in and portability. To add more complexities into this equation, cloud providers take all open source innovation, add their infrastructure and sell it as managed services Generally open source community thrive on offering the product for free, but making money with consultancy on running the products. But the cloud providers are taking up this pie. This has resulted in open source companies changing their models and companies like MongoDB, Redis and few others rolling out newer features only on their managed services preventing cloud vendors from taking advantage. 

### What Vendor Lock-in means in the context of cloud?

So what does vendor lock-in mean in the context of the cloud? Choosing a public cloud provider's services that are not based on standards and are not easily portable to other cloud providers. At a fundamental level, Infrastructure As A Service ( IAAS) is the foundational layer that exists in all cloud providers and there are bare metal server offered. Building solutions with just this would mean would be the safest and easiest way to avoid vendor lock-in. But this also means we would not be able to leverage all the innovations being rolled up by cloud providers. Hence a more nuanced way of approaching the vendor lock-in situation must be thought through.

As we stand in 2020, here are the major pros and cons that are there with Cloud Vendor Lock-in. And these are not widely different from the previous decades of choosing an IBM or Oracle or Microsoft stack of products. Like the famous saying, no one gets fire for choosing IBM, it is now, no one gets fired for going with AWS. 

**Advantages of going with a single vendor approach for Cloud**

1. Easier management of products, services, support and effective governance. This is a major advantage.

2. Better integration between the vendor products could result in fewer complexities and over-heads.

3. Even though it may not be open standards, building solutions on top of new products offered by cloud services would result in bringing products to the market faster and a lot of cost savings in terms of less maintenance and monitoring etc with less infrastructure and operation support. 


**Issues associated with Vendor Lock-in**

1. Companies are tied to the vendor and may be in the mercy of vendor when it comes to pricing etc. One change in the pricing by a few dollars could result in a huge cloud bill that can make or break companies, especially in the start-up world.

2. When a particular cloud vendor was evaluated and chosen, there might not have been a significant cost difference. But over time when the other vendor reduces the price, the option of taking advantage of cost reduction by moving to other vendors may not be possible. Also if there is a tight integration between multiple products in a single vendor set-up, negotiation for better deals in terms of discounts may not be possible. Few companies use this flexibility and offer mild threats to cloud vendors about porting out to other companies to negotiate better deals and that is no more possible. 

3. There is no easier way to migrate unless there was a conscious smart decision taken during the initial architecture and design phase to reduce the impact of the lock-in. Migrate to a new cloud in worst cases could very well be a re-write.


### What does it mean to avoid vendor lock-in? Multi-cloud , but  

Building solutions that can be easily run on multiple cloud providers. For really large companies at the scale of Google, Microsoft, Uber, Netflix etc, the multi-cloud makes absolute business sense. It looks like a no-brainer that multi-cloud must be the default mind-set. But then the challenge of building solutions already in the cloud is pretty complex and the multi-cloud approach would take up significant time and resources in terms of managing such a complex setup. 

Even though Cloud has been there for a decade now, companies are only now adopting at a really large scale. Resiliency, Availability and Recovery are being thought and designed mostly at a region level amongst multiple availability zones and cross-region availability and management of resources are already proving to be challenging in terms of cost and associated overheads. With so many complexities in a single cloud setup, thinking about a multi-cloud approach unless otherwise there is a strong business case to move multi-cloud may not be recommended for all.


### So how to think about Vendor Lock-In and ways to minimize it

**1. Design applications with a hexagonal architecture** 

Hexagonal architecture has a nicely layered approach wherein the business logic and entities are core to the system,  adapters and controllers are a way to interact with these objects. And the technology and vendor components are built at the peripheral layer and can be replaced relatively easier. For example, if we are to use Amazon DynamoDB, do not introduce DynamoDB and its interaction in every layer. Any and every part of the application needs to connect to a data layer to get data in a standard way and this data layer will be the only layer that talks to DynamoDB. So if we need to replace DynamoDB, the data layer contract would not change and other application components would continue to talk to the data layer in the same way. But the implementation at the data layer may change to talk to MongoDB instead of DynamoDB. So a conscious approach of clever design and architecture could help us deal with this problem better.

**2. Choose services from other cloud vendors when they deem fit.**

Depending on the use-case, if there are few services from other cloud vendors that are good, choose them. For example, Google Cloud may offer better services in terms of Machine Learning / AI etc and even though an organization may be currently all in AWS, it would make sense to choose Google Cloud for the use-case and make the best use of it. Even though the resulting overhead and complexities may be extra, it would still make absolute business sense.

**3. Think of workflow portability**

Instead of thinking of designing for workload portability, workflow portability could be another aspect to think of. For example, the choice of Infrastructure As Code ( IAC ) for AWS could very well be Terraform instead of AWS's own Cloud Formation. With Terraform, even though there may be additional work required to write scripts for another vendor stack, there is a way to manage and re-use the workflow within Terraform for multi-cloud scenarios. 



### Standards and Interoperability in Cloud World may take a long time

Standards and Interoperability may not be the main focus for market-leading cloud vendors like AWS or Microsoft because honestly, they would want customers to be in their offerings. There is no incentive for these companies to think of standards. It is with vendors like  Oracle, IBM Open Shift pushing the multi-cloud and standard offerings because that is their only way to stay relevant in the market. Google Cloud and others champion Kubernetes and containers and often claim how it helps to avoid vendor lock-in. But then running Kubernetes is going to take significant resources at the end of the day. Also, the implementation of Resources Identity Access and roles is different with every vendor and Cloud Security is a big focus area for all companies and dealing with security in multi-cloud setup would make things even complex.  If AWS comes up with Lambda, Google comes up with Cloud Run which is based on open standards of docker though some aspects of it may not be open at all. Google Cloud tries to champion K-Native movement as well.So there is no point in choosing services that have open standards and easily portable at this point of time. The Cloud adoption is still maturing and it may take a while to get there. 

### So what should we do in 2020? Go All-in with single cloud provider 

Every tech company would want to retain or lure the pie from others to increase their revenue. And the approach of each vendor is mostly self-serving.So it becomes necessary to carefully consider all these points and build architecture in a way that it is relatively easier to port the applications if the situation demands. There is no point in not building services that are cloud-native leveraging all good innovations in the cloud just to avoid vendor lock-in. Every extra line of code written or extra server to be managed will always incur cost in terms of resources, maintenance and overall management. 

The overall yearly IT spend of organizations is currently around 1.8 trillion dollars around the world and the cloud vendors have a together annualized run rate of just 80 billion dollars. So there is enough pie for all cloud providers to grow and hence would not be particularly looking to increase the cost. I feel for the next 5-10 years, Vendor lock-in would not matter as the cloud adoption is still evolving and everyone is figuring out this beast. So unless otherwise there is a clear business case, in my opinion, I would not urge you to think of multi-cloud or vendor lock-in. The focus must be building applications to wow customers and end-users with smart architecture and design choices that can help in porting out to a different vendor relatively easier if the situation demands such a step in future.     
    