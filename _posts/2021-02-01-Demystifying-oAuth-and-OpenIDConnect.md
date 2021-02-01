---
published: false
---
Authentication and Authorization as a concept has been there for a really long time. oAuth is the most standard way in which authorization is implemented and OpenID Connect is a preferred mechanism for authentication. In this podcast , we will Demystify oAuth and OpenID Connect - why , what and how. Listed below are the various topics that are briefly touched upon



**1. Introduction**

- Difference between Authentication and Authorization 
- Identity Service Provider is nowadays widely used due to the increasing complexity and evolving nature of  Security 
- Many Identity Providers help in this regard and offer to take the undifferentiated heavy lifting of authentication/ authorization, Managing infrastructure and Minting Tokens 
- List down popular ones. Auth0, Okta, Firebase, AWS Cognito, Azure AD etc 


**2. History of Authentication**

-Basic Authentication
-Windows OS based Authentication / SSO
- SAML for Enterprise Apps / Web SSO
- How SAML worked?
- SAML Assertion returning XML with details of the user and other details
- SAML is for Web SSO
- Explosion of applications and consumer-facing 
- Facebook and the emergence of social apps and authentication based on that. 
- oAuth / oAuth2 
- OpenID Connect 


**3. oAuth/ oAuth2**

-Why oAuth?
-oAuth is not a protocol, but just a specification 

-Main actors/elements 
- Resource Owner
- Client
- Authorization Server 
- Resource Server 
- Tokens


**4. Comparing oAuth with an analogy of check-in to a Hotel** 

- Reference from Okta blog 
- Guest - Resource Owner
- Client - Hotel 
- Authorization Server - Hotel Reception 
- Tokens - Room Key, Key Guards

 
- Privileged users have access to more than just rooms 
-Client Registration - clients register with oAuth providers 
-Authorization Grant - Owner approves the authorization and grants access
-Scopes and Claims 
-Tokens - JSON Web Tokens JWT pronounced JOT :)
-Different parts of JSON - JWT token. Header / Claims and Signature 
- Talk briefly abt Access Token and Refresh Token 


**5. Types of Grants/Flow** 

- Authorization Grant Access Code Flow - Access Code is received from Authorization Server in the front end and backend uses code to fetch the access token 
- Implicit Flow Grant  - Front end directly connects to the Authorization Server, and gets back the access token directly without additional calls. Happens via the web client in the browser. Not very secure due to Man in the middle attacks
- Resource Owner Password Grant - Native, trustable,  first-party client 
- Client Credentials Grant - Server to Server authentication 
- Evaluate the flow required and decide accordingly on the approach


**6. OpenID Connect**

-What were the challenges with oAuth
-How OpenID Connect helps with the Authentication mechanism 
-OAuth 2.0 + Facebook Connect + good parts of SAML 2.0 
- Companies that support OpenID Connect 
- oAuth - Authorization Framework while OpenID Connect and SAML is Authentication 
- In addition to access token and refresh tokens, id token is now being used 
- Facebook uses oAuth 2.0 while Google and Microsoft use OpenId Connect 

**7. Tokens**

- ID Token - has details about user and permissions 
- Access Token - has details about access required to access Resource Server
- Refresh Token - helps to refresh the duration of access tokens without the need for authentication again 
- Refresh Tokens - where is it possible and how are they getting refreshed
- Not possible with SPA and web apps 
- Makes sense with native applications where silent token refresh is possible 
- Where Refresh Tokens make sense and where it is difficult  
-Token Revocation and Policies. Webhooks that be can be triggered by IDP when the password is changed or expired. It can help to blacklist tokens in a cache or database and then manage till the time the token expires. 
-Implementation challenges with Tokens

**8. Scope And Claims**

- Scope in the context of oAuth 
 - Scope is permission 
- Commonly defined Scope in oAuth:
	OpenID
        Profile
        Email
        Custom Scope 
- Claims is a set of key-value pair about the user's permissions and other attributes 
- Custom Claims can be added to a JWT token as well and they can be populated with user data while creation of a token

**9. Tokens vs Cookies and its Security Implementation** 

- Session Cookies 
- Stateful, session information maintained in-memory or database
- Cookie was stored in a browser cookie. Make it HTTP only will help to avoid CSRF attacks. 
- Cookie gets sent as part of every request from the domain 
- Explain CSRF attack scenario
 -How Cookies was used before?
- What challenges Cookies posed? 
- How Tokens solved these problems?
- Tokens were stateless, scalable, decoupled and good performance 
- Token Web Storage - local or session storage 
- XSS - Cross-Site Script attacks when input validation is not sanitized 
- Tokens can be stored in Cookie as Token for better security
- Tokens are larger in size due to security and cryptography signatures  compared to Cookies 

Other security issues with OAuth 
- Token hijacking - use of CSRF token along with state parameters can help
- Leakage through re-directs. So white list redirect URI's
- Client secret can be revealed 

**10. How Tokens are validated by Resource Server / API** 

- Tokens are decrypted using keys 
- Validation of whether tokens are clean or tampered 
- Expiration time can be checked and allowed/rejected accordingly 
- Also signature verification can be done 
- Get the public key certificate and fetch the kid and other properties to do signature validation. 
- In case of the server to server communication, minimal validation is enough using client id and secret 

**End** 

-Re-cap of the journey from Basic Authentication to Open ID Connect 
- We have come a long way from registering on every website to using oAuth to help with the registration of data 
- Data Privacy has certainly improved 
- Security Posture keeps increasing every day and challenges continue to remain
- IDP help with the authentication authorization security 
- Federation is another aspect where user identity systems from multiple backends are connected for a seamless unified backend user registry system 






