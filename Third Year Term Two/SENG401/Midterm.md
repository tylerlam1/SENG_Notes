# Software Architecture

# Slideset 1

# Software Architecture

Software Architecture is the dunamental concepts or properties of a system in its environment embodied in its elements, relationships, and in the principles of its design and evolution. In other words, it refers to the fundamental strcutres of a software system and the discipline of creating such structures. Each structure comprises softwrare elements, relationships, and the properties of both elements and relations.

We can say it is internal design. It's the overview of the system that proviudes guiding principles during the implementation of the system. It is a framework by which to reason about each part of the system.

The purpose of software architecture is to:
* Provide a high-level overview of the system that guides the smaller implementation details
* Software architecture lays out the foundation for addressing non-functional requirements

The goal is to:
* Manage the complexity of the system
* Provide for evolution of the system over many years
* Enable effective development by software engineers

The motivations of software architecture:
* Move away from waterfall development
* Increased use of Agile
* Less use of bare metal configurations
* Mixed results with internal hosting
* More use towards cloud

Software Architecture is a long-lasting commitment to the evolution of a software system. Changes in underlying structure leads to new software architectures. Architects and software engineers have a hand to play in the development of modern day software architectures.

# Slideset 2

Functional requirements is what a system does. Non-functional requirements is how the system does it.

Here are a list of non-functional requirements:
* Accessibility - consider users of different needs, and support alternate modes of interaction.
* Usability - how easy is it to interact with the system?
* Security - user authentication & authorization
    * Data privacy is affected by the flow of data within the system and each place where the data is stored
    * Malware and viruses protection should be considered throughout the system where there are external entry points
    * Physical security is a concern based on who has access to the hardware
* Regulatory Requirements - Regulations may constrain how data is handled
* Performance - can mean many things, like the following
    * response time
    * Query per second (QPS)
    * Simultaneous users
    * Concurrent queries
* Reliability - ability of  component to function as designed for a specified period of time. Can be expressed as mean time between failures.
* Redundancy - duplicating system requirements (like backup systems)
    * Hot backup - backup performed on data while database is actively online (no downtime)
    * Warm backup - server is on, but not performing any work
    * cold backup - database is offline and not accessible
    * voting - comparing data between systems
* availability - what percentage of time is the systems available
* maintainability - how long it takes to restore the system or fix defects

Latency is the time interval between cayse abd effect. Bandwidth is maximum rate of data transfer across a given path.

* Resilience - ability to continue functioning under adverse conditions.
* Scalability - ability to handle an increasing workload
    * vertical - add more RAM/processors
    * horizontal - add more computers
* data consistency - is data the same everywhere?
* audability - ability to review what has occurred in the system
* portability - can the same software be moved to different environments?
* extensibility - ability to rework system, add extensions
* testability - ability to verify correctness of components
* ability to develop across a large team
* ease of refactoring - is it easy to make large scale changes?

# Slideset 3

Most modern day software systems are required to be modifiable and have good performance. They may also need to be usable, secure, interoperable, portable, and reliable. We can use different SW architecture evaluation/assessment methods to determine the suitability of the system.

1. Informal/ad-hoc architectural evaluation
* Learn from past
* You can catch errors and problems early
* fast when architecture is on paper

There are clearly better ways to evaluate the architecture than using the ad-hoc way. 
* SAAM (Software Architecture Analysis Method)
    * Scenario-based evaluation
* ATAM (Architecture Tradeoff Analysis method)
    * Scenario-based evaluation with tradeoffs
* SACAM (Software Architecture Comparison Method)
    * Business goal-driven comparison of architecture alternatives
* CBAM (Cost-benefit analysis method)
    * Focus on economic aspects 

## ATAM (Architecture Tradeoff Analysis Method)

* ATAM is a method for evaluating software architectures relative to goals specified by quality attributes
* ATAM exposes architectural risks that potentially inhibit the achievement of business goals
* provides insight on how quality goals can be possibly traded-off against each other

These are the following quality requirements:
* Traceability - elicit rationale of design decisions
* risks - alternatives that might create future problems
* sensitivity points - alternatives for which a slight change makes signficiant difference in a quality attribute
* tradeoffs - deicisions affecting more than one quality attribute

Deliverables:
* The architectural approaches (styles)
* A utility truee
* set of scenarios generated and subset that were mapped into architecture
* A set of quality-attribute specific questions that were applied to architecture
* a sset of identified risks and non-risks
* a set of sensitivity points

Different aspects of Architecture Tradeoff Analysis Method (ATAM):
1. Quality attributes - non-functional requirements
2. Architectural Views - facilitate discussion of changes, and facilitate discussion of changes
3. stakeholders
4. scenarios - describe how a system will be used, evolved, crashed, etc.

Phases:
1. Presentation - includes business drivers requirements, constraints, architectures, quality attribute, scenarios
2. investigation and analysis - prioritization, application, risks, risks, senstivity points, trade-offs
3. Get all stakeholders involved and priortized scenarios
4. gather findings

# Slideset 4

* Reuse is the use of parts of one product to facilitate the development of a different product
    * opportunistic reuse
    * systematic reuse

Here are some of software engineer's best practices:
* Develop iteratively
* Manage requirements
* Use components & Architectures
* Model visually (UML)
* Continously verify quality
* Manage change

Opportunistic reuse is to identify where existing subsystems and components may be reused based on their interfaces.
* Look for similar interfaces
* Modify new interfaces to improve the fit
* Replace candidate interfaces with existing ones
* Map the candidate subsystem to existing components

Systematic reuse is the deliberate modelling of reusable components
* reuse of expertise
* reuse of standard design and algorithms
* reuse of libraries or classes or procecdures
* reuse of functions and libraries
* use of frameworks

Design Patterns reuse the standard design of others. 
* An adjunct to existing (OO) design methods.
* A means to make designs more robust

## Function Library

A set of already existing functions that can be invoked within a program.

## Class Library

A class is a unit of abstraction and implementation in an OO programming language.

## Component

A component is an encapsulated software unit with specified interfaces and explicit context dependencies that provide client applications with access to its services.

A component can be deployed independently and is subject to composition by third parties. Components can range in size from simple functions to entire application systems. 

CBSE - Component based software engineering. The philosophy is to buy and not build. There's emphasis on composing software systems with a black box approach, and using integration rather than implementation. Components are stand-alone service providers, and a component can be independently deployed and subject to composition by third-parties. An example of a component could be a Windows executable, COM objects, or be dynamically linked to any Windows application.

COTS - Commercial Off-The-Shelf system. COTS systems are usually complete application systems that offer an API. Building large systems by integrating COTS systems is a viable development strategy for some types of system.

## Framework

A framework is a resuable design of all or part of a system that is represented by a set of abstract classes and the way their instances interact. It's a skeleton of an application that can be customized by an application developer.

It defines how objects work together to get something done. It defines the superclasses or public interfaces for the objects you develop. It's the skeleton of the application that can be customized by an application developer.

## Product Family

A set of products with many commonalities

## Product Population

A set of products with many commonalities but also many differences

## Product Line

A software product line is a set of software-intensive systems that share a common, managed set of features satisfying the specific needs of a particular market segment or mission and that are developed from a common set of core assets in a prescribed way.

## Framework vs Library

A framework is a large complex body of code that embodies knowledge on how to write successful applications within a well-defined problem domain.

A library is a body of code you call and use when you feel appropriate

# Cloud Computing

The following is the application stack:

1. Application
2. Data
4. Runtime
5. Middleware
6. O/S
7. Virtualization
8. Servers
9. Storage
10. Networking

IaaS, SaaS, and PaaS are different levels of service.

1. On premises - means to have the computing resources contained in your own physical space.
2. Private Cloud - when you separate the application layers from the computing layers - both managed internally.
3. IaaS - provides third party services for network hardware, storage space, virtualization, and servers. AWS and Azure are examples of this.
4. PaaS - provides a platform to develop applications. Manages the operating system, middleware, and runtime. Example is Heroku.
5. SaaS - provides the application hosted on the cloud. Example is Office 365 Suite.

In on-prem and private cloud, all layers of the application stack are managed by you.

* Hybrid Cloud - combination of on-prem and private cloud with some public cloud services.
* Virtual private cloud - a subset of a public cloud that is private.
* DCaaS (Data Center as a service) - colocation of computing infrastructure in a data center managed by a third party.

# Model View Controller

* Model View Controller is an architecture pattern that separates the application into three components
    * Model, which represents the data and business logic
    * View, for presenting the data to the user
    * Controller, for handling user requests
* Separation of Concern is the biggest takeaway here
* MVC can be used in a thin-client
* MVC can be split onto the client

The benefits of MVC are the following:
* Separation of concern
* Simultaneous development of components
* Loose coupling
* Testability
    * Test components separately
    * Smaller focused tests
    * Especially userful for the Model and Controller
    * Can test business logic without mixing presentation style
    * Can test controller with mocked model

The pitfalls:
* Potential code inconsistency across components
* Complexity in tracing code
* Overhead/boilerplate
* Scattered code for each feature

MVC does not scale components separately. It's used within an application, rather than a large scale architecture.

# Event Sourcing

Event Sourcing is an architectural pattern in which the state of the system is stored as a sequence of modifications. 

When appending data you could add some metadata like a timestamp. As event sourcing will most often be used in distribute dsystems, it is important that IDs are unique across all systems. UUID is a common way to generate unique IDs in distributed systems as it is guaranteed unique without needing to coordinate between machines.

Event sourcing is:
* Sequence of mutations to the state
* Immutable and irremoable events
* Event stream is source of truth

Benefits:
* Audit trail
* Full replay
* Debuggability
* Bring up new data stores

Problems:
* Data inconsistency
* Requires careful attention
* Breaks ACID (atomicity, consistency, isolation, durability)
* Queries are difficult
* Hard to understand

Guidelines when defining events:
* Too fine-grained vs too coarse
* de-serialization costs
* generally define events to match user intent
* events should be self-contained and complete
* follow CRUD (it can be faster due to cache and prevents SQL injection)

In general, choose wisely where to apply event sourcing. 