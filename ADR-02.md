### Architectural Decision Record

### Security architecture

## Context and Problem Statement	
The complaint management system are required to process sensitive data, including personal information, organisation data etc. The system must protect this  information from unauthorised user, unauthorised data modifications and disclosure while ensuring data availability for consumers, staff and admin.
The key challenge is to design a security architecture that supports role-based access and maintainability while complying with confidentiality. The key statement in building this architecture is “ which security architecture is best to protects confidential data while supporting role-based access to secure interactions within the system?”
## Decision Drivers
*	The system must protect sensitive data in accordance to the GDPR.
*	The system must prevent any unauthorised access across the organisations.
*	It must supports role-based access control (RBAC).
*	It must integrate smoothly with layered architectural style.
*	It must supports API communication.

## Considered Options
*	Custom authentication and authorisation system
*	Firebase Authentication system with role-based access control and JSON Web Token
*	OAuth


## Decision Outcome
Chosen option: “Firebase Authentication system with role-based access control and JSON Web Token (JWT)” because it provides a secure and industry standard authentication while maintaining simplicity. Firebase Authentication provides a JSON token upon successful authentication, enabling a secure API access. Backend is reenforced RBAC to ensure user can only perform actions that are permitted by their roles. This approach aligns with layered architecture in (ADR-01) and supports the multi-tenant approach in (ADR-03).

## Consequences
*	Firebase is a trusted service that handles user’s sensitive information such as email and password.
*	Good, because this approach integrated seamlessly with layered architectural style.
*	Good, because the system can reduce responsibility by allowing third party service to handles authentication.
*	Good, because JWT authentication enables a high security.
*	Bad, because it increase the reliance on a third party service.


## Pros and Cons of the Options

### Custom authentication and authorisation system

*	Good, because it offers a full control over the authentication and authorisation system.
*	Good, because it does not rely on a third party service.
*	Bad, because it risk security since a good cryptography handling requires expertise.
*	Bad, because it increases effort to maintain.
*	Bad, because incorrect implementation can lead to breach in GDPR compliance.

### OAuth 2.0
*	Good, because it is scalable since it is separated by layers.
*	Good, because it is an industry standard for API authorisation.
*	Good, because it offers excellent scalability since its token system can handles a large number of users.
*	Good, because it is widely accepted and used across industries.
*	Bad, because it increases reliance on a third-party service.
*	Bad, because implementation is complex since it involves multiple flows for different scenarios.





## Reference

1.	Should You Use OAuth 2.0? Pros and Cons. (2023, November 21). Digital Information World. https://www.digitalinformationworld.com/2023/11/should-you-use-oauth-20-pros-and-cons.html
   



