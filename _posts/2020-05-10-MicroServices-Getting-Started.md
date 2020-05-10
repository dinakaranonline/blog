---
layout: post
title: Microservices Getting Started
author: dinakaran
image: assets/images/microservices.jpeg
published: true
---
Microservices is all the rage in the last few years. And there are some hot discussions on Microservices vs Monolith. One of the biggest challenges with microservices is with regard to when what and how. It is very easy to get carried away by the hype and start trying to implement everything with microservices. So careful consideration is required on when to go for microservices.
![]({{site.baseurl}}/https://miro.medium.com/max/1400/1*1hBwhZ--xEVY35z5owT1Qw.jpeg)
#### Microservices from Application Architecture Point of View

When anyone starts reading about microservices, one of the first and foremost concept that we read about is Bounded Context. There are a ton of articles around this. But as we dig deep, there are other architecture challenges that need to be considered. Picking the right architecture design pattern for your microservices can make things better or for worse. Also Designing architectures and pattern around Data is one of the biggest challenges that we face with microservices coupled with consistency and the trade-off with each approach.

So a careful consideration from application design and architecture standpoint with pros and cons is rather necessary. 

#### Microservices from Infrastructure Point of View

Think Microservices, Think Containers. And with containers coming into the picture, a PAAS solution seems to be the most obvious choice. So the moment microservices is being considered, it brings along with it a fairly large number of build, deployment and run-time architecture challenges that are normally associated with distributed application architectures.

In the world of microservices, infrastructure cannot be an afterthought. All microservices should be designed with the infrastructure aspect of how the various systems need to be put in place and how each of them interacts with each other. 

#### Who takes the decision for Microservices 

One of the biggest challenges in deciding ongoing towards the Microservices route. Application Developers are traditionally well aware of building monolith applications and Infra Operation Team is well versed with deploying monolith using the well-established industry best practices. But with microservices, there is an air of ambiguity - it is no longer a decision that can be taken either by application developers or ops team in isolation. Only people who understand all the different aspects of building microservices - be it from application architecture, infrastructure and DevOps will be able to understand fully the intricacies and nuances associated with building microservices.

In my personal view, with the advent of cloud, provisioning of new services and resources is becoming easier. Application Developers crossing their 'bounded' context and learning more about infrastructure and DevOps would be the most preferred way to understand and fully embrace microservices. They will still need infra ops and DevOps team, but one person having end-to-end is extremely important for understanding scale, complexity and challenges associated with architecture, design, implementation and management of services.