# ENSF 480 Final Exam

## Data Modelling

Data modelling is the process used to define and analyze data requirements needed to support business processes within the scope of corresponding information systems of organizations. In other words, its used to help design the data systems needed by a company.

This can be broken into three stages:

### Early Analysis Stage
Conceptual Data Model
* A set of technology independent specifications about data
* Used to discuss initial data requirements with business stakeholders

### Early Design Stage
Logical Data Model
* Translation of conceptual data model into logical model
* Documents the structure of the data that can be implemented

### Late Design Stage
Physical Data Model
* Translation of logical model to database table

Usually, a conceptual data model is a DFD (Data Flow Diagram) model. This does not show the natural "structure of the data"

That's where the ERD (Entity Relationship Diagram) comes in.

A ERD is good for quickly obtaining information about the structure of a system's database.

## Entity
A entity is a abstract concept within a data model. Each representing one or more instances. Each entity is represented by a box and a singular name. The following a way to properly model out a data structure:

1. Identify the domain entities. 
2. Identify whether or not the terminator information needs to be accessed.
3. Analyze each entity. Is it a composite entity? If so, then it has a 'many cardinality' associated with it.
4. Identify the relationship between entities.
5. Identify the type of relationship.
6. Identify the multiplicity among the entities. 
7. Identify the optionality among the entities relationships. (Whether its mandatory).

## Data Dictionary

A listing of all the data elements, and organized alphabetically. It describes each data element in a precise, rigorous manner. It describes the following:
* Meaning of all data flows and data stores
* Composition of data flows
* Composition of stored data

It specifies the values and units of data, and helps define the relationship between data stores in conjunction with the ERD.

Here are a couple fields in a Data Dictionary:
* Name: Primary name of the composite data item
* Aliases: other names for the data item
* Where used: data transforms that use the composite data item
* How used: the role of the data item
* Description: a notation for representing data
* Format: specific information about data types

<img src = "Images/DataDictionaryExample.png" width = 550px>

## Software Process Models

The Software Development Process or Software Development Life Cycle is splitting of software development activities into different phases.

A example would be going from: Analysis -> Design -> Code -> Test

Pros:
* Simple
* Independency of phases
* Suitable for smaller projects

Cons: 
* No output until end
* Hard to manage requirement changes
* High degree of uncertainty and risk
* Not suitable for large projects

### Iterative Models

Pros:
* Early working product
* Easier to manage the requirement changes
* Easier for testing and debugging
* Lower risk factor

A example would be going from: Design -> Implement -> Analysis -> Design -> Implement -> Analysis ....

### Spiral Model

Pros and Cons:
* Same as simple linear models, with focus on risk analysis

## Prototyping

* Prototyping can improve the quality of requirements and specifications provided to developers. It can help reduce cost of requirement as errors will be detected earlier.

## Agile Development

1. The highest priority of the Agile Development Cycle is to satisfy the customer through early and continous delivery of valuable software. 
2. Welcoming changing requriements, even late in development, Agile Development harnesses change for customer's competitive advantage
3. Deliver working software frequently, from a couple of weeks to a couple of months
4. Business people and developers must work together daily throughout the project
5. Build projects around motivated individuals. Give them the environment and support they need.
6. The most efficient way of conveying information is face-to-face
7. Working software is the primary measure of progress
8. Agile processes promote sustainable development. Sponsors, developers, and users should be able to maintain a constant pace indefinitely.
9. Continous attention of technical excellence and good design enhances agility.
10. Simplicity - the art of maximizing the amount of work done is essential
11. The best architecture emerges from self-organizing teams
12. At regular intervals, the team reflects on how to become more effective

### SCRUM

1. 15 minutes every day, talk about what have I done, what do I need to do, and how will I do them? 
2. Every couple of weeks, release working software, review of requirements "backlog"

## Testing Approaches

1. V-Model (Waterfall Approach)

From my understanding, you pretty much plan and design everything first, and then implement all at once. Then you integrate, test, and verify, and go back to designing if need be. 

2. Test-Driven Development

Test-Driven development, as the name suggests, mean you design a small piece of code, implement it, test it (using J-Unit), and progressively add on to it by further producing code and testing.

## Rapid Application Development (RAD) Approach

This approach aims to:
* produce high quality systems quickly, primarily via incremental and iterative evolutionary prototyping.
* Using development tools like: GUI builders, CASE tools, and Database Management System (DBMS).
* Intensively involves the user
* Controls the project control using "timeboxes". If the project starts to slip, emphasis is to reduce requirements to fit the timebox, not increase the deadline
* Use Joint Application Design (JAD) approach

## Rational Unified Development Process (RUDP)

The rational unified process is structured along two dimensions:
* Process components: Production of a specific set of artifacts with well-defined activities
* Time: Division of the life cycle into phases in iterations

Both dimensions must be taken into account for a project to succeed.

The Process Component Dimension includes the following activities: Requirement, Analysis, Design, Implementation, and Testing

