# Software Architecture

Software Architecture lays out the foundation or address non-functional requirements. 

There are different goals of software architecture.
- Manage complexity of the system
- Provide for evolution of the system over many years
- Enable effective development by software engineers

There are different aspects of software architecture.
- Structure of the system
- 
-

Often times, a software solution must scale and be economically viable. Therefore, it is important that we need a solid foundation on which the solution grows on. A system that takes 1-2 years to build may be in production use for 10+ years.

## Functional vs Non-Functional Requirements
A function requirement describes what a system should do. Focus on what the user wants.

A non-functional requirement describes how a system work. In general, a non-functional requirements cover all that functional requirements don't cover. They specify criteria that judge the operation of a system, rather than specific behaviours. Usually something not seen by user.

Example of non-functional requirements:
* Performance
* Scability
* Capacity
* ...

### Accessibility

* Consider users with different needs
* Support alternate modes of interaction
* Also consider mobile devices, slow connections, etc

* Direct supoort within the system
* Or indirect support via assistive technology

### Usability

* How easily can the interact with the system
* Self documenting (no manual needed)
* Can be measured within a specific context - effectiveness, efficiency, satisfaction

### Security

* User authentication 
* User authorization

You get authenticated to get authorization. Authorization is the giving of specific rights to a program, and authentication is checking if the person is who they say they are. 

- Data privacy is affected by the flow of data within the system and each place where data is stored

- Malware and viruses protection should be considered throughout the system where there are external entry points

- Physical security is a concern on who has access to the hardware

## Regulatory Requirements

* Regulations may constrain how data is handled
* May impose reliability requirements
* Can your developers access data?
* Must data be encrypted?
* In what jurisdictions can your data be stored?

## Performance

* Performance can mean many things.
* For now, let's consider:
    * Query per second
    * Response time
    * Simultaneous users
    * Concurrent queries

## Reliability

Reliability is the ability of a component to function as designed for a specified period of time. Often expressed as Mean Time Between Failures.

## Redundancy

* Duplicating system requirements
* Generally refers to backup systems
* Compared to scalability, redundancy focuses more on backups
* Patterns
    * Hot: Live, processing data - replicating data to other machine. Two machines may be in the exact same state. Failure rates may be exactly the same.
    * Warm: Ready to sync to hot machine.
    * Cold: Backups when the hot machine is offline
    * Voting: systems being outvoted can be considered problematic (data doesn't agree with others)


## Availability
* What percentage is system available?
* Often expressed in number of 9s
    * 99%
    * 99.9%
* high availability can be achieved with redundancy
* Affected by system resilience and also intentional downtime such as hardware replacement

## Maintainability

* how long it takes to restore the system or fix defects
* for hardware, often measured as mean time to repair
* consider how readily spare parts are acquired

## Resource Constraints

* processors
* memory
* disk space
* disk performance
* power consumption
* network latency
* network bandwidth

## Resilience

* ability to continue functioning in adverse conditions

## Scalability

* Ability to handle an increasing workload
* Two types:
    * Vertical
    * Horizontal
* Scalability should be a core part of the architecture

### Vertical

This means to scale up. Add resources to a system component, like more RAM or processors. More common historically, software may be agnostic to vertical scaling. Affecting by Moore's Law, and usually requires downtown. 

### Horizontal

This means to scale out. DOne by adding more machines, and increasing capacity of a distributed system. Can be done seamlessly, and the right software architecture allows massive scaling. Sometimes you can scale out without awareness of it being done within the component. 

For example, each part of a system can be doing its own thing. Essentially, you're splitting the workload.

## Data Consistency

Is the data consistent among different machines? Data takes time to travel and you want to make sure all machines have the same data.

## Auditability

* ability to understand what occurred within the system
* Provides safeguards as it detects errors, a means to recover
* can be implemented at different levels, explicit software function to log events

## Portability

* can move to different environments

## extensibility

* ability to extend the system (browser has webpages, extensions, etc)
* can you add new features without disrupting other parts of system

## testability

* vertification of the correctness of components
* quality assurance
* support for
    * unit tests
    * component tets
    * integration tests

## Software Architectures

Why should we evaluate software architectures? 
* Learn from the past -> patterns
* exists early -> catch errors/problems early - early is better (less cost)
* Choice of each architecture that influences the project, from coding to learn to schedule
* fast while architecture is on paper

When? 
* the architecture is specified

What is the outcome?
* is it suitable? Does the quality meets your goal? can it be built with resources
* which of two or more are most suitable?

We need to know what is important (these are non-functional requirements).

Scalability is not a scalar.
* which attributes are affected by architecture
* which of our goals are okay? which are problematic?

Software Architecture Patterns.

## Architectural Evaluation

* Most of the modern software systems require to be modifiable and have good performance. 
* What exactly measures modifiability, usability, security, performance, and reliability mean?
* Can a system be analyzed to determine these qualities?
* How soon can analysis occur?

When determining whether an architecture satisfies its requirements often involves:
* Being very explicit about what the requirements are and how they are reflected in architecture
* understanding where one has to make trade-offs between different design alternatives
* applying analysis wherever possible to determine consequences
* mediating between desires of different stakeholders

When evaluating software architecture, we can do informal/ad-hoc architectural evaluation

There are better evaluation methods than ad-hoc evalution:
* SAAM (Software Architecture Analysis Method) - Scenario based evaluation
* ATAM (Architecture Tradeoff Analysis Method) - Scenario based evaluation with focus on trade-offs
* SACAM (Software Architecture Comparsion Method) - Business goal-driven comparison of architecture alternatives
* CBAM (Cost-Benefit Analysis Method) - Focus on economic aspects

### ATAM

ATAM is a method for evaluating software architectures relative to goals specified by quality attributes. ATAM exposes architectural risks that potentially inhibit the achievement of business goals.

ATAM not only reveals how well in architecture satisfies particular quality goals, but also provides insight on how quality goals can possibly traded-off with one another.

### Goal 

Evaluate whether the design decisions satisfactorily address quality requirements
* Traceability: Elicit rationale of design decisions
* Discover risks: Alternatives that might create problems in some quality attribute
* Sensitivity Points: Alternatives for which a slight change makes a significant difference in a quality attribute
* Tradeoffs: Decisions affecting more than one quality attribute

## Components and Frameworks

Reuse is the use of parts in one product to facilitate the development parts of the application with different functionalities.

* Accidental Reuse
    * To identify where existing subsystems and components may be reused based on their interfaces.
* Systematic Reuse
    * Reuse of expertise, standard designs, algorithms, functions, libraries, frameworks

A component is an encapsulated software unit with specified interfaces and explicit context dependencies that provide client applications with access to its services.

A framework is a reusable design of all or part of a system that is represented by a set of abstract classes and the way their instances interact. The skeleton of an application that can be customized by a app dev.

## Product Line
* Product Family: A set of products with many commonalities and new differences
* Product Population: A set of products with many commonalities but also many differences
* Product Line: A set of software intensive systems that share a common, managed set of features satisfying the specific needs of a particular market segment or mission and that are development from a common set of core assets.

## Beyond Design Patterns
* Function Libraries
* Class Libraries
* Design Patterns
* Components
* Frameworks
* Software Product-Lines

## Frameworks

A reusable design of all or part of a system that represented by a set of abstract classes and their instance interact. 
* Defines how objects work together to get something
* Defines the superclasses or public interface
* The skeleton of an application that can be customized by an application

Frameworks interact with application logic through:
* Subclassing

For example, let's investigate the *Inverstion of Control* principle. Frameworks invert the role of control between the application and infrastrcture. With a framework, you are no longer in control. The framework controls the way your application works.

Frameworks has some notions like Events (mouse), hooks (exit) and subclassing (frame). Application lives inside the framework.

## What is Feedback?

* Giving your opinion on someone elses work.
* Feedback is a part of exchanging ideas. Take an idea, and exchange ideas about.
* How we continue to improve something... etc

## Why collaborate?
* Divide and conquer
* People have different skills, people can together build much better project
* People don't hve to learn everything

But who should collaborate?
* Software Engineers, Hardware Engineers
* Clients (they have input on what they want)
* Project Manager
* Marketing - how you can eventually sell a product?
* Testers, designers, owners, etc.

Product Managers at Google look at the long term. What are people interested in? What are similar products doing? They focus on everything around the user input. Project Managers are different than Product Managers - they look at timelines, etc.

The UI/UX Designers focus on making the product on making everything appealing to the user.

We can also focus on more general groups:
* Stakeholders - People who have an interest in the work, because they use it, fund it, or are involved in the industry.
* Domain Expert - someone knowledge in one or more of the system you work with either the main product, or a system which you reply; e.g. database admin, reliability engineer, business logic expert.

## Rules for Successful Collaboration
* Communication
* Being open-minded, open to other perspectives
* Listening attentively
* Don't take things personally - separate *ideas* from *people*
* There are no "heroes" in a team effort - don't depend on a single person. Everyone has a stake in the results, etc.

Collaboration does not mean:
* Consensus - Not about everyone agreeing. It's about exchanging. It's not necessarily about bringing in all ideas, but talking debating and talking about ideas
* Sometimes it means you have to be bold - Doesn't necessarily mean having a fully-fleshed idea (business idea, etc).
* Sometimes external forces (other classes, etc) may affect your decision. i.e. choose if you want to make something really fancy, or simply straightforward

How can collaboration fail:
* Lack of communication - You MUST speak up. 
* People have different expectations - sometimes just result of lack of communication (i.e. people build same thing, team members have a different idea of the resulting product)

Doesn't matter if you're a 4.0 student or what not, your ideas won't succeed if you don't communicate, test and discuss them. They need contact to the real world.

## Design Documents and Diagrams

Each style has their own design documents template, and style.

A design document is important as it:
* Provides a description of the system for stakeholders
* Validation that the intended design meets stakeholder needs

Document metadata - explains why you are actually doing this design.
* Basically identifies the contents the contents of the document
* Easy to reference from other documents
Has authors, contributors, title, date (indicates how fresh your system is), purpose, background reading, and context (broader description to how this fits into everything else in your company). 

A design document describes what you intend to build. 
* Requirements
* Components
* Architecture
* How it interacts with user
* How data is stored
* Technologies used
* how is it deployed?

## Rest APIs

Representational State Transfer (REST) is a set of constraints on the structure of messages used to access a remote service (generally web services).

REST is intended for client-server applications. The client initiates the request, and the server performs the action and responds.

There is a Uniform Interfaces, where access to all resources follows the same pattern. Also, there's a shared communication protocol and data format.   

REST is considered stateless. This means that the server does not store state, and the client is responsible for providing all data during each request.

How this connection works should be transparent to the client. Whether the client talks to the server or an intermediary should be transparent to the client. This enables proxy, load balancing, and caching.

A URI (Uniform Resource Identifier) represents a single resource. It is possible to cache a response, but some responses can be marked as non-cacheable.

The URI structure easily allows for adding new resource type. URIs are easily parsed and handled by different servers. 

## Concurrency

Concurrency is when multiple independent computations are occurring at the same time. A process is an instnce of a program being executed on one machine. A thread is the smallest unit of execution within a process. A process comprises one or more threads running concurrently. This is what the operating system understands and runs. 

We will be investigating architectures inside a process. Once you have an idea how architectures work inside a process, you can easily apply it to multiple architectures.

The default architecture, shared memory, is error prone. Within a process, most code are not designed for concurrency. 

If you have inter-process communication, it forces you to split up the data. It forces you to be conscious about the interaction between programs. Memory passing is the sensible option here.

### Process & Threads

* O/S starts a process
* A process starts as one thread
* One thread can spawn others
* O/S schedules threads

* A process has one copy of the code (compiled code)
* Each process has one copy of static, global, and literal data
* Each process has one shared block of memory for the heap
* Each thread has separate memoryfor its stack

### CPU Scheduling

* CPUs run thread
* Common CPUs 2-4 cores (up to 8 hyper-thread)
* A CPU run threads from one or more processes
* Scheduling is done by the O/S; process is mostly unaware

When you have badly parallelized code, results are the segmentation fault. Other things that happen are:
* random order of values in output vector
* Crash
* Undefined behaviour leaving data structures unknown

An example is incrementing pointer, another thread is re-allocating data.

Thread-safe is code that can be run concurrently in more tha one thread while producing the correct results.

Strategies for thread-safe:
* Mutex
* Preallocate memory
* Better code design

### Idempotency

When one can be repeated without changing without the result. If you perform an operation once, or ten times, you still get the same result. It's usually spoken in terms of internet requests. 

The basic premise is that if you don't modify shared state, you can't get into concurrency trouble.

Better code design is to:
* Write idempotent functions
    * All inputs are immutable
    * The return value hold all results
* Follow this pattern throughout your code
* Except... in the one function that coordinates the concurrency
* Clearly document the concurrency
* Write code that is easy to read and understand

When you're preallocating, you're isolating output data from each thread. 

Something important to consider is non-determinism. This is acceptable in some cases, but make sure you're using a data structure that encourages this (set) as opposed to something like a vector.

## Message Passing

Communcation is done by sending messages to other threads over a unidirectional channel. Typically you should use available libraries for this and not write out own.

```C
template <typename T>
class Channel {
    public:
        void send(T value);
        void close();
        void std::optional<T> read();
}
```

Worker thread - get a function, and then run it.

Message passing is different from shared memory (the channel itself is shared memory). The message passing isolate the concurrency and shared messages inside the channel. 

Shared memory:
* Low overhead
* Keeps a single copy of the data
* Synchronization of memory access
    * Blunt tools
    * Clever approach
    * Lock free algorithms