### Architectural Decision Record

### Data Architecture

## Context and Problem Statement
The complaint management system must support multiple organisation while ensuring the data for each organisation is isolated, has consistent structure and easily retrievable by users. Data must be easy to modify as each organisation may requires an additional field.
The key question in deciding the data architecture is “ How should data be structured to support  multi-tenancy while maintaining security? ”. 

## Decision Drivers
*	Must support multi organisation data isolation.
*	Must ensure only authorised user can access all data.
*	Must be clear and easy for developers to understand.
*	Must easily integrated with Node.js.
*	Must support fast read and write operations.
*	Must support png documents for attachments.

## Considered Options
*	Relational Database
*	No SQL database
*	File-based data store

## Decision Outcome
Chosen option: “No SQL database” because it supports flexible documents schemes, easy implementation and has a logical separation of data for each organisations. It aligns with layered architecture and supports scalable expansion. Firestore enables each complaint to be stored in a single document, reducing complexity.


## Consequences
*	Good,  because it avoids complex data structure.
*	Good, because Firebase authentication can be integrated
*	Good, because each organisation can store their data in a separate and isolated collections.
*	Bad, because it cannot handle complex relational queries

## Pros and Cons of the Options

### Relational Database (SQL)

* Good, because it enforced data consistency
*	Good, because it can handle complex queries
*	Bad, because manual expansion is needed to scale
*	Bad, because scheme rigidity slows down evolution

### File-based data
*	Good, because it is simple
*	Bad, because it does not scale
*	Bad, because it does not support a variety of documents
*	Good, because it can handle a large amount of data
*	Bad, because it has limited query capabilities.
*	Bad, because it does not support relationships between dataset
*	Bad, because it has no security and access control

More Information

Reference

1. 	Team Estuary. (2025, October 13). Flat File Database: Definition, Examples, Advantages, and Limitations. Estuary. https://estuary.dev/blog/flat-file-database/



