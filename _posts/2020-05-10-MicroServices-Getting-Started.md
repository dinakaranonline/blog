---
layout: post
title: MicroServices Getting Started
author: dinakaran
image: assets/images/microservices.jpeg
published: true
---
MicroServices is all the rage in the last few years.And there are some hot discussions on Microservices vs Monolith. One of the biggest challenge with micro services is with regard to when , what and how. It is very easy to get carried away by the hype and start trying to implement every thing with microservices. So a careful consideration is required on when to go for microservices.

![]({{site.baseurl}}/https://miro.medium.com/max/1400/1*1hBwhZ--xEVY35z5owT1Qw.jpeg)

#### Microservices From Application Architecture Point of View

When anyone starts reading about microservices , one of the first and foremost concept that we read about is Bounded Context. There are ton of articles around this. But as we dig deep , there are other architecture challenges that needs to be considered. Picking the right architecture design pattern for your microservices can make things better or for worse. Also Designing architectures and pattern around Data is one of the biggest challenge that we face with microservices coupled with consistency and the trade-off with each approach.

So a careful consideration from application design and architecture stand point with pros and cons is rather necessary. 

#### Microservices From Infrastructure Point of View

Think Microservices , Think Containers. And with containers coming into the picture , a PAAS solution seems to be most obvious choice. So the moment microservices is being considered, it brings along with it a fairly large number build , deployment and run time archiecture challenges that is normally associated with distributed application architectures.

In the world of microservices , infrastructure cannot be an after thought. All microservices should be designed with infrastructure aspect of how the various systems need to be put in place and how each of them interact with each other. 

#### Who takes the decision for Microservices 

One of the biggest challenges in taking a decision around going towards the Microservices route. Application Developers are traditionally well aware of building monolith applications and Infra Operation Team is well versed with deploying monolith using the well established industry best practices. But with microservices, there is an air of ambiguity - it is no longer a decision that can be taken either by application developers or ops team in isolation. Only people who understands all the different aspects of building microservices - be it from application architecture , infrastructure and DevOps will be able to understand fully the intracices and nuances associated with building microservices.

In my personal view , with the advent of cloud , provisioning of new services and resources is becoming more and more easy. Application Developers crossing their 'bounded' context and learning more about infrastrucutre and devops would be the most preferred way to understand and fully embrace microservices. They will still need infra ops and devops team, but one person having end-to-end is extremely important for understanding scale , complexity and challenges associated with architecture , design , implementation and management of services.
