# Architectural Decision Record
## Design Pattern (Structural)

### Context and Problem Statement
The Complaint Management System manages complaint that may have nested elements such as attachments and notes. The system requires a design that supports scalability as complexity increases. A hierarchal structure is needed rather than a flat model. The structural design pattern must represents a single complaint or group related elements uniformly and support extensibility without modifying existing code. Which design pattern supports a hierarchal structure while maintaining simplicity?

			
### Decision Drivers
*	The design must be scalable as complaint hierarchy grows
*	The design must have an excellent readability and separation of concerns
*	The design must be easy to expand without modifying existing code
*	The design must handles a single and a grouped complaint with uniform structure


### Considered Options
*	Composite pattern
*	Adapter pattern
*	Bridge pattern
*	Proxy pattern	
*	Decorator pattern
*	Flyweight pattern

### Decision Outcome
Chosen option: "Composite pattern” because it allows the complaint management system to represent the hierarchal of a complaint structure. For instance, each complaint may have an attachment that should be easy to read and to scale the hierarchy. It enables handling a collection of complaint or individual through one single interface.

### Consequences
*	Good,  because it can work with complex trees structures and be more convenient using polymorphism and recursion. For example, each complaint can have an attachment and a sub-notes.
*	Good, because new element types can be introduces without breaking existing code, which supports the system scalability through a wider regions and multiple companies.
*	Good, because recursive operations provides a clean and simple implementation.
*	Bad, because it is difficult to provide a common interface for functionality that differs too much
*	Bad, because it can overkill if the system only requires a simple structure.



## Pros and Cons of the Options
### Adapter pattern
*	Good,  because it  allows interface separation from business logic of the program
*	Good, because external system could be integrated by using API into the system.
*	Bad, because code will be complex since new interfaces and classes must be introduce.
*	Bad, because it will overkill the code since its just simpler to change the service class.
*	Bad, because it does not model a hierarchical structure which is essential for the complaint management system


### Bridge pattern

*	Good, because platform-independent classes and apps can be created
*	Good, because the code has a high level of abstraction and it does not expose platform detail
*	Good, because it supports multi-region data rules without exposing the platform detail
*	Good, because new abstraction and implementation can be introduced independently
*	Bad, because the code will be more complex by applying the pattern to a high cohesive class.
*	Bad, because adding a bridge layer introduces an unnecessary layer the system that does not solves anything.

### Proxy design pattern

*	Good, because service object can be controlled without the client’s knowledge on it. The system can control sensitive information.
*	Good, because proxy will work even if service object is not ready.
*	Bad, because the response from service might get delayed
*	Bad, because it does not support hierarchical structures
*	Bad, because the code will be complex since a lot of classes need to be introduced

### Decorator design pattern
*	Good, because it can decouple classes that invoke operations from classes that perform these operations.
*	Good, because new commands can be added without modifying existing code.
*	Good, because a simple command can be turned into a complex one
*	Bad, because it introduces a new layer between senders and receiver.
*	Bad, because the code will be complex to build
*	Bad, because it does not provides a hierarchical structure that is needed in the system

### Flyweight design pattern
*	Good, because it saves a lot of memory if the program uses similar objects
*	Bad, because it will trade CPU for RAM making it slower.	
*	Bad, because it does not support hierarchical structures that the system needed.

## More Information
### Reference

1.	Refactoring Guru. (n.d.). Flyweight. Refactoring.guru. https://refactoring.guru/design-patterns/flyweight



