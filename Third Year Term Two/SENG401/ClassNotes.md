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
