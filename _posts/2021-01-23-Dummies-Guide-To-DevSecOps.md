---
published: false
layout: post
author: dinakaran
image: assets/images/DevSecOps.jpeg
categories:
  - Programming
---

**1. Why DevSecOps**

- Bringing security to the agile DevOps process. 
- Engage security from the beginning.
- Shift security to the left. 
- Compliance too becoming critical.


**2. How?**

- People: Stakeholders, teams 
- Process: Standardise, workflows. Governance, Cadence. Security Review 
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

- Avoid the big bang approach. Take one or two items and build from there.
- Start with the low hanging fruit, and pick easier to fix things
- Do not enable every single security rule that it results in too many issues reported resulting in none being fixed due to other conflicting priorities
- All tools integrated into the pipeline without too much of manual work outside of the existing workflow.


**6. Tools**

- Static Code Analysis 
- Lint cools like CFNLint, CFNNag and other validation tools 
- IAC Rules scanning
- Vulnerability scanning
- Secret Manager, Key Manager, auto rotation 
- WAF


**7. Some app-level security issues and solutions**

Some Cloud-related security risks that need  attention 

- 1. DDOS attack on web applications.
-    Enable WAF and better secure coding practices
- 2. S3 buckets left open to the public
-    Fine-grained IAM access control and permissions to the bucket 
- 3. Security credentials checked into the source repository
-    Static Code Analysis can bubble up these issues.
- 4. Databases wide open with SSH access 
-    IAC security rules to restrict access via Security Groups etc.
-  5. IAM policies having way too much access, not restrictive enough, ending with * etc
-    IAC security rules to validate and ensure such broad access are never allowed.


**8. Other security aspects**
- Observability
- Traceability 
- Confidence and Repeatable 
- Infrastructure and Network security monitoring. Alarms and alerts
- Compliance - Encryption, SSH certificates rotation, whitelisting/ blacklisting


