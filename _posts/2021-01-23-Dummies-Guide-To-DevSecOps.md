---
published: true
layout: post
author: dinakaran
image: assets/images/DevSecOps.jpeg
categories:
  - Programming
title: Dummies Guide to DevSecOps
---
DevSecOps is a relatively new term coined that focus on the colloboration between Application Development, Operations and Security Teams coming together to deliver applications and software in an agile fashion in an iterative, faster and secure way.

In this podcast, we discuss the reason why DevSecOps have come into focus in the last few years. And for teams to start adopting DevSecOps practices , what are different aspects , perspectives and approaches that need to be considered is also briefly touched upon. Threat Modelling is the starting point to understand the security posture , identifying gaps and priortize critical aspects that need attention. We also discuss on the tools, technology and automation that are required for successfully building DevSecOps practices.

I hope the information discussed here helps to get a jump start on DevSecOps.


**1. Why DevSecOps**

- Bringing security to the agile DevOps process 
- Engage security from the beginning
- Shift security to the left
- Compliance too becoming critical


**2. How?**

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
- Get developers used to the process and see how it helps in their development workflow.As part of product development sprints , include one or two security targets that needs to be managed. 
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

Some Cloud-related security risks that need  attention 

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
- Confidence and Repeatable 
- Infrastructure and Network security monitoring. Alarms and alerts
- Compliance - Encryption, SSH certificates rotation, whitelisting/ blacklisting
