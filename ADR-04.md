# Architectural Decision Record
## Design Pattern (Creational)

### Context and Problem Statement
The Complaint Management System requires an architecture and design pattern that supports long-term scalability and maintainability. As the system continues to expand, more complaint types and modules may need to be added without modifying existing code.
Therefore, the problem is: Which design pattern best supports easy extensibility, loose coupling, and clean separation when new complaint types or objects are introduced?

			
### Decision Drivers
*	The design pattern must be easily scalable in the future for example, adding more classes in the future.
*	The design pattern must reduce coupling between client code and concrete classes.
*	The design must support flexibility and maintainability. 
*	The design must be reusable in future projects
*	The pattern must support code expansion without modifying existing code

### Considered Options
*	Abstract Factory pattern
*	Concrete Factory pattern
*	Singleton pattern
*	Composite design pattern
*	Command design pattern

### Decision Outcome
Chosen option: "Abstract factory method", because it provides the best decoupling between creation and usage. It allows the system to create a family objects without being tied to a concrete class. This will allow the system to scale if new classes are needed in the future without changing any existing code. The complaint management system is expected to handle complaints from multiple companies such as airlines, banking and a telecom company which may require different information in their complaints. Furthermore, the CMS has to comply with different compliance such as Europe, UK and is expected to expand to other regions. Therefore, new compliance can be easily added in the future. 

### Consequences
*	Good, because it reduces coupling, making it more flexible than creating objects directly
*	Good, because binding application to a specific classes is not required.
* Good, because the code can be reusable allowing concreate classes creation
* Good, because the pattern allows new object creation without modifying the code making it flexible.
*	Good, because it supports multi-organisation and multi-region.
*	Bad, because  it adds complexity to the code due to number of classes needed
*	Bad, because it could lead to a tight coupling  between factory and concrete class.
  
### Pros and Cons of the Options
### Singleton
*	Good, because it has control of access over the instances
*	Good,because global variables for instance is not required
*	Good, because it can be subclassed
*	Good,because  it as a variable number of instances
*	Good, because it is flexible
*	Bad, because it introduces tight coupling
*	Bad, because it isolates components so each components needs a different testing
*	Bad, because it limits scalability
*	Bad, because it may leads to data inconsistency



### Concrete factory pattern

*	Good, because reduces object creation directly
*	Good, because it allows subclasses override.
*	Good, because to centralise all construction method.
*	Bad, because it allows only one type of object
*	Bad, because it requires existing code modification if a new object is needed
*	Bad, because does not support multi-organisation extensibility

  
### Composite design pattern

*	Good, because it simplify  hierarchical data structures
*	Good, because it slows uniform treatment of individual objects
*	Good, because it is easy to add new components, making it flexible
*	Bad, because it increases complexity
*	Bad, because it may leads to performance overhead due to large hierarchy.
*	Bad, because common interface might me over-generalised, leading to invalid operations
*	Bad, because it can add unnecessary complexity for a simple structure

  
### Command design pattern

*	Good, because it can decouple classes that invoke operations from classes that perform these operations.
*	Good, because new commands can be added without modifying existing code.
*	Good, because a simple command can be turned into a complex one
*	Bad, because it introduces a new layer between senders and receiver.
*	Bad, because the code will be complex to build


## More Information

### Reference
1.	Command. (2014). Refactoring.guru. https://refactoring.guru/design-patterns/command





