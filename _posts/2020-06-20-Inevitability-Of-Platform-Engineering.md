---
title: Inevitability Of Platform Engineering
date: 2020-06-20 00:00:00 Z
categories:
- Programming
layout: post
author: dinakaran
featured: false
image: assets/images/platforms.jpg
---

With the advent of Cloud Computing and Microservices, it solved a lot of challenges that are usually associated with the on-prem setup and monolith applications. And the whole industry tried to leverage the benefits provided by Cloud and Microservices and CI-CD DevOps automation movement. While this has generally been good, it came with its own set of challenges, in terms of too much plumbing that each team needs to take it upon themselves.


The focus has been also on the small two pizza teams who own, runs and manages the design, development and infrastructure/operations as well. The movement to products from projects has resulted in a lot of product-led thinking with complete autonomy and decisions de-centralized to the smaller teams. With microservices, the biggest advantage touted was that every team building services can choose their stack and need not follow the standards. But has also resulted in each product 2 pizza teams coming up with own set of platform, tools and processes because they have been fully empowered. While there are certain advantages to this approach, the amount of groundwork that requires to be done for such a setup is huge and each teams coming up with their standards and disparate choice of technologies, tools and process without reason will make things unmanageable as the teams and product lines grow. 

To address, companies building products and growing in cloud and microservices have tried to come up with the concept of platform engineering. Generally, a platform is a term associated with companies that offer an array of services, features which other companies may use to build products and services. For example, AWS is a platform in which people build products and services. Same with Facebook or Twilio, they are essentially platforms and offered in a Software As A Service model using which other companies can build.

### Why Platform Engineering?

Platform Engineering is mostly a term that is generally associated within a company that provides composition and integration of a set of tools, process, standards setup, defined and in some cases exposed as an API/ features that various product and services can consume to empower developers and product teams. Platform teams within a company or large organization focus on building and providing a base set of plumbing in terms of infrastructure, tools and processes that product teams can take advantage of. 

Other than the infrastructure and standards, another obvious scenario is when product teams end up building the same or like feature again and again. When a feature built by one product team is being built by other teams too, it is a prime candidate for moving to the platform layer. 

### How Platform Engineering is different from DevOps? 

But what essentially does the DevOps aka the Infrastructure or Operations Teams do? The term DevOps means different things to different people. For one, DevOps is a mindset and culture shift towards development and operations seamlessly unified. With the advent of the product based thinking and services and each team having full autonomy, all product teams start to re-invent the wheel. DevOps - Infrastructure or Operations are not centralized anymore as they tend to slow down the innovation. While all of these felt good initially, this has also resulted in a different challenge. Every product team coming up with own stack of Cloud Provider, Microservices strategy - Containers or Functions As A Service - Serverless, Choice of Infrastructure Automation, Ways of building and deploying code, addressing security and running automation tests, code quality scanning tools, ways to manage secrets, set up of logging infrastructure, databases, backups, house cleaning activities etc. 

Having a separate team for infrastructure and operations had its challenges and moving to the DevOps approach of teams managing stuff themselves has resulted in a lot of boiler-plate work that each team need to be involved. Recruiting and scaling the teams also could be challenging since within a company there may be 10 product teams and each of them having their standards, choice of languages, framework etc. All these challenges resulted in the thinking of building platforms that internally serve various product teams. So essentially, product teams are customers for the platform teams. 


### What should Platform Teams do?

So what does the Platform Team should do essentially? A Platform team provide necessary building blocks upon which product teams can build innovative products and services.  Roles and Responsibilities of the Platform team can include the following. But the list is indicative.

1. Provision Infrastructure easily using API's or set of process, tools and automation of CI-CD pipeline. Choice of Cloud Provider, Containers and Orchestration, Version Control, CI-CD tools etc. 
2. Boilerplate plumbing tools for Observability and this involves the likes setting up of logging infrastructure, tracing and monitoring, secret and API key management, health checks etc 
3. Build and provide common features that are used by many product teams. While features can still be managed by separate microservices team, the features built and delivered by platform teams do not generally end user-facing. Platform teams do not build features but provide features like key management, feature flag management, self-service tools for managing access etc.
4. Test Automation frameworks, Security Scanning and Static Code Analysis tools etc.
5. Self-service tools for most of the use-cases with little to no-co -ordination. 


### General guiding prinicples for Platform Team

1. Help Product Teams build and innovate faster, help them with feature velocity.
2. Not constraint product teams too much with standards that hamper innovation. 
3. Offer well-written documentation, standards and code samples, conduct a lot of sessions and training on why the platform team was built in the first place and how product teams can take advantage of them. 
4. It can be opinionated but should be open to product teams feedback for constant improvement. 

There should never be a situation where product teams request for features from platform teams and end up waiting for the same. Teams should be autonomous and fully independent. So does Platform team own infrastructure then? Not really. The ownership still rests with Product Teams. Platform Teams just provides a tool kit to make the life of product teams managing software less cumbersome. 


### So when does having a Platform team makes sense?

Well, there is no right answer to this. But generally speaking, larger the number of product teams and engineers, the kind of problems and patterns listed above starts to emerge. It comes to a point where it becomes very difficult to manage infrastructure, process and tools used by various teams. It is all over the place and there is a feeling of not being in control. This is probably a good point in time when the platform team can start to make sense. How many platform teams should a company have? Starting with a single platform team with a defined set of target customers, who are essentially the product teams would be a good starting point. Learnings from running the platform team could help to refine and move further and if necessary.

### Find building and managing platform too complex, go the PAAS way?

Ready-made Platform As A Service solutions ( PAAS) provided by vendors is probably an easier way to get started. Pivotal Cloud Foundry and RedHat Open Shift offer PAAS products that provides an opinionated way of building software. It has ready-made built tools that help to easily get started. These products have built a lot of abstractions that help to avoid the complexities of running things in the cloud. These PAAS products place few constraints on the way software or products can be built and they come with their trade-offs. 

As the cloud ecosystem matures and the same kind of problems and challenges emerge, there will be new products that will be built to make the software development more seamless and not daunting.          

**References**

[https://martinfowler.com/articles/talk-about-platforms.html](https://martinfowler.com/articles/talk-about-platforms.html)

[https://xodiac.ca/2020/04/27/do-I-need-a-platform-team.html](https://xodiac.ca/2020/04/27/do-I-need-a-platform-team.html)

[https://softwareengineeringdaily.com/2020/02/13/setting-the-stage-for-platform-engineering/](https://softwareengineeringdaily.com/2020/02/13/setting-the-stage-for-platform-engineering/)

[https://hackernoon.com/how-to-build-a-platform-team-now-the-secrets-to-successful-engineering-8a9b6a4d2c8](https://hackernoon.com/how-to-build-a-platform-team-now-the-secrets-to-successful-engineering-8a9b6a4d2c8)

[https://alexgaynor.net/2015/mar/06/devops-vs-platform-engineering/](https://alexgaynor.net/2015/mar/06/devops-vs-platform-engineering/)

[https://medium.com/dm03514-tech-blog/enterprise-architecture-engineering-platforms-a1b456019d03](https://medium.com/dm03514-tech-blog/enterprise-architecture-engineering-platforms-a1b456019d03)


[https://www.infoq.com/articles/galo-navarro-platform/]( https://www.infoq.com/articles/galo-navarro-platform/)
