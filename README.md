# Architectural style Decision Record

## Context and Problem Statement

The complaint management system requires a clean and well-defined architecture that supports non-functional requirements such as usability, scalability, reliability. The chosen architectural style must clearly divide responsibilities across user interface, business logic, data access and database. The architectural style will be decided with a singular key question which is “which architectural style supports a clean separation between responsibilities and fulfilled the non-functional requirements?”

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* The architectural style must be easy to scale.
* The architectural style must be simple in deployment and debugging
* Must have a clear separation in responsibility
* Easy to be evolved into a service-oriented structure
* Easy to maintain and deploy
* Easy for developers to understand
* Must have a high security and prevent data exposure



## Considered Options

* Layered (N) Architectural style
* Three tier Architectural style
* Microservice Architectural style
* Client-server Architecture
* Event-Driven Architecture
  
## Decision Outcome

Chosen option: "Layered(N) architectural style", because it provides a clear separation of responsibilities  and concerns, improving readability and maintainability. This architectural style separates responsibilities into 3 layers which are user interface, business logic and data access layer. It satisfy all the criteria for non-functional requirements and functional requirements.

<!-- This is an optional element. Feel free to remove. -->
### Consequences

* Good,  because changes made in a layer will not affect other layers.
* Good, because it is easy to scale since each layers can be scale individually.
* Good, because it has clear separations of concerns, improving maintainability
* Good, because testing can be made individually for each layer.
* Bad, because request must go through every layer even if it is not required.
* Bad, because it can become rigid if boundaries between layers is not enforced.



<!-- This is an optional element. Feel free to remove. -->
## Pros and Cons of the Options

### Layered architectural style


* Good, because easy to evolve into service oriented architect in the future.
* Good, because components can be reused in the future.
* Good, because it has a clear separation into layers. Each layer can go through a software development life cycle.
* Good, because it’s easy to maintain and debug since it has a boundaries between each layer.
* Good, because each layer can be tested independently improving its reliability and performance.
* Good, because it is easier to scale since it is separated by layers. Each layer can scale individually based on the required performance.
* Bad, because every process has to go through every layer making it slow.
* Bad, because having layers will increase complexity for a simple application.
* Bad, because it is too rigid when dealing with changes. Any small changes can effect multiple layers leading to potential issues with integration.


### Three tier architectural style


* Good, because it is scalable since it is separated by layers.
* Good, because data is secured. Database is not directly accessible in the client tier, making it more difficult for unauthorised person to access data.
* Good, because it is easy to maintain and modified.
* Bad, because network traffic will increase if a separated proxy is used.
* Bad, because additional network communication between tier increases latency
* Bad, because any changes is client tier requires rebuilding and retesting the entire app, making it not flexible.

### Microservice architectural style

* Good, because every service in independent, making it easier to develop.
* Good, because it is easy to scale independently based on demand.
* Neutral, because it allows technology diversity and different programming languages.
* Good, because it has fault isolation. Since every service is independent, a failure in one service does not effects the others.
* Bad, because managing multiple services is complex since each service needs its own software development life cycle.
* Bad, because it introduces inter-service communication issues since it communicates over a network.

### Client-server architectural style

* Good, because it allows for centralized management since admin has complete control over management.
* Good, because this architectural method can easily adjust to changing requirements from integrating new technologies to evolving user needs.
* Good, because this method ensure continuity even during hardware failure or network disruption, making it reliable. 
* Bad, because the cost is extremely high since servers are expensive and it is required since home computer does not meet the requirements needed and it does not support for specific functions.
* Bad, because designing, setting up and managing a client server network is complex. This complexity also increases with three-tier system where a careful coordination is required.

## More Information

## Reference

1.	GeeksforGeeks. (2021, June 10). Advantages and Disadvantages of ThreeTier Architecture in DBMS. GeeksforGeeks. https://www.geeksforgeeks.org/dbms/advantages-and-disadvantages-of-three-tier-architecture-in-dbms/
2.	GeeksforGeeks. (2024, August 13). What are the Advantages and Disadvantages of Microservices Architecture? GeeksforGeeks. https://www.geeksforgeeks.org/system-design/what-are-the-advantages-and-disadvantages-of-microservices-architecture/

