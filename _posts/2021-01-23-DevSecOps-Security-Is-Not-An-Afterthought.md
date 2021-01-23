---
published: true
layout: post
author: dinakaran
image: assets/images/DevSecOps.jpeg
categories:
  - Programming
title: DevSecOps - Security is not an afterthought
---
DevSecOps is a relatively new term coined that focus on the collaboration between Application Development, Operations and Security Teams coming together to deliver applications and software in an agile fashion in an iterative, faster and secure way.

In this podcast, we discuss the reason why DevSecOps have come into focus in the last few years. And for teams to start adopting DevSecOps practices, what are different aspects, perspectives and approaches that need to be considered are also briefly touched upon. 

Threat Modelling is the starting point to understand the security posture, identifying gaps and prioritize critical aspects that need attention. We also discuss the tools, technology and automation that are required for successfully building DevSecOps practices.

You can listen to the podcast episode here 

<iframe src="https://open.spotify.com/embed-podcast/episode/5QauBb0hlWs8ijjNSe9TwJ" width="100%" height="232" frameborder="0" allowtransparency="true" allow="encrypted-media"></iframe>


Streaming in popular platforms too here. Please subscribe.

**[Spotify](https://open.spotify.com/show/4gFFUZ8Vl3dVKDOFwauRIe)**
**[Apple Podcast](https://podcasts.apple.com/in/podcast/master-of-none/id1545755804)**
**[Google Podcast](https://podcasts.google.com/feed/aHR0cHM6Ly9hbmNob3IuZm0vcy80NGRiYzU2MC9wb2RjYXN0L3Jzcw?sa=X&ved=2ahUKEwin0_Lm2OrtAhVfyHMBHZyHD3gQ9sEGegQIARAC)**


**1. Why DevSecOps**

- Bringing security to the agile DevOps process 
- Engage security from the beginning
- Shift security to the left
- Compliance becoming critical

**2. How DevSecOps**

- People: Stakeholder buy-in and Getting Teams onboarded 
- Process: Workflow standardization and Documentation
- Technology: Tools and automation


**3. Threat Modelling**

- Threat Modelling to be done before implementing DevSecOps
- Help organizations to understand the kind of attacks the organization or the application can be exposed or targeted 
- Identify gaps in the current security posture and then decide on the prioritization areas where the security needs to be improved
- Prioritise and plan accordingly


**4. Learning** 

- Security is a shared responsibility. Everyone in the team and organization have a  responsibility towards security. 
- Secure coding practices 
- Knowledge of OWASP Top 10
- Sharing of recent security incidents and impacts from the industry that are  relevant


**5. Implementation**

- As a result of Threat Modelling,analysis and prioritization, define 
  - Targets
  - Rules
  - Enforcement
  - Toolset

- Avoid the big bang approach. Take one or two items and build from there
- Start with the low hanging fruit, and pick easier to fix things
- Get developers used to the process and see how it helps in their development workflow. As part of product development sprints, include one or two security targets that need to be managed. 
- Do not enable every single security rule that it results in too many issues reported resulting in none being fixed due to other conflicting priorities
- All tools integrated into the pipeline without too much of manual work outside of the existing workflow.


**6. Tools**

- Static Code Analysis, Dynamic Code Analysis
- Penetration Testing
- Lint tools like CFNLint, CFNNag and other validation tools 
- IAC Rules scanning
- Vulnerability scanning
- Secret Manager, Key Manager, auto rotation 
- WAF


**7. Some app-level security issues and solutions**

Some Cloud-related security risks that need  attention. Depending on the type of environment, the issues may vary. But i'm giving here a brief list so that we get a good understanding of how the process looks and works in action 

- **Risk 1**:   DDOS attack on web applications.
-    Solution:  Enable WAF and better secure coding practices

- **Risk 2**:   S3 buckets left open to the public
-    Solution:  Fine-grained IAM access control and permissions to the bucket 

-  **Risk 3**:  Security credentials checked into the source repository
-    Solution:  Static Code Analysis can bubble up these issues

-  **Risk 4**:   Databases wide open with SSH access 
-    Solution:   IAC security rules to restrict access via Security Groups etc.

-  **Risk 5**: IAM policies having way too much access, not restrictive enough, ending with * etc
-    Solution:  IAC security rules to validate and ensure such broad access are never allowed.



**8. Other security aspects**
- Observability
- Traceability 
- Infrastructure and Network security monitoring. Setting up of Alarms and Alerts
- Compliance - Encryption, SSH certificates rotation, whitelisting etc

I hope the information discussed here helps to get a jump start on DevSecOps.
