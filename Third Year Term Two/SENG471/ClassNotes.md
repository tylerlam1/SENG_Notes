# Software Engineering Requirements

## Lecture 1

Software Engineering is the application of a systematic, disciplined, quantifiable approach to the development, operation and maintenance of software.

There are five components of Software Engineering:
* Requirements (Like a blueprint - similar to constructing a house)
* Design
* Developing - Also called construction
* Testing
* Maintenance

Each subsequent step is dependent on the preceding step. For example, the design is a product of the requireents. Your development is dependent on your design. 

Here are some potential job titles associated with Software Engineering:
* Developer
* Quality Assurance (QA)/Tester
* Project Manager
* Operations
* Analyst

Requirement Engineering is the condition and capacities regarding a software problem. Requirements are needed to solve a problem or achieve a goal. In technical terms, it is a set of activities to identify and communicate the purpose of a software system and the contexts in which it will be used. Therefore RE acts as a bridge between the real world and stakeholders affected by the software system and capabilities afforded by software-intensive technologies.

Requirement Engineering is not a single activity or phase. It is an iterative process.

Five tasks must be done (EASVE):
1. Elicitation - Acquiring information related to software systems
2. Analysis - Analyze this information to formulate problem
3. Specifications
4. Verification/Validation - Verify (Are they correct?)
5. Evolution - Maintain requirements documents for future updates (Changing of requirements)

Please be advised that not _all_ information should be included. Only the important/needed information. You cannot skip any steps - it's important that all steps are included.

At each part of your RE steps, you need to have a verification/validation step to ensure each step is correct. This process means that you may have to go back in steps.

### Functionality vs Non-Functionality
* User-friendliness is a non-functional requirement

### Reverse/Forward Engineering

Moving forward in the Software Lifecycle is considered to be forward engineering. Going backward is considered reverse engineering. An example of forward engineering is going from *Requirements Analysis* to *Design*.

### Cost of Requirement Errors

As you get deeper into the Software Lifecycle, it becomes increasingly expensive to remediate issues associated with requirement errors. There is as much as a 200:1 cost ratio between finding errors in the requirement stage versus the maintenance stage.

You typically want to dedicate a *reasonable* amount of your resources on the Requirements Engineering. This is about 10% - 20%. 

## PowerPoint Solutions (What is RE?)

1. Identify and communicate
2. Purpose of the software system
3. Stakeholders affected by the software system
4. A set of activities
5. contexts in which it will be used
6. Real-world needs
7. Capabilities and opportunities afforded

## Are These Requirements? 

Requirements is a condition or a capacity that your system *should/must/shall* fulfill to solve a problem or achieve an objective. 

1. The elevator shall only change directions, when stopped at a floor.
    a. Yes. 
2. When the elevator within 20cm of the sensor's position, the sensor sends a high signal; otherwise a low signal.
    a. No. This moreso talks about what your system does. This is an implementation, not a requirement.
3. The system of controlling the elevator shall occupy no more than 5.0 GBytes of RAM.
    a. Yes
4. We would like a new system of controlling the elevator that is easier to use than the old one.
    a. No

## Requirements (Types of)

1. Enterprise Requirements
    * Reasons
    * Constraints
2. Functional Requirements
    * Features
3. Non-functional requirements
    * Constraints
4. Client/User requirements
    * Problems and constraints

1. Why
2. What
3. How
4. Who

The bullet numbers correspond to each other.

### The WRSPM Model

W - Work
R - Requirements
S - Specifications
P - Program
M - Machine

Application Domain - Where the ideas/constraints are situated.
Machine Domain - where your code is situated.

Validation - is everything covered to the best of your knowledge?

### Requirements Example

* Word Bank - UCID, passwords, users, system admins, authorization process, hacker, encryption algortihm, password files, cache, content, security, sockets, application process

#### Things Machine Cannot Observe
1. Hacker
2. System admin
3. Authorization process
4. Passwords files
5. Process
6. Application
#### Shared things
1. UCID 
2. Passwords
Since UCID + Password = Users, it's a bridge between non-machine and machine
#### Things private to the machine
1. Users
2. Encryption algorithm
3. Cache content
4. Security sockets
### Software Requirements Specification
The following are purposes:
* Contractual for development
* Baseline for evaluation
* Baseline for change control

Audience of SRS:
* Clients
* Your team (Developers/testers/architecture/maintenance)
* Business analysts
* Regulators
* Managers (Project)

### SRS: Degree of Formality
For a tiny project (where you have one programmer):
* It may be 2 months of work
* 5 page memo
* purpose is to clarify programmer's understanding
* From a management view, SRS is irrelevant. All the resources have already been allocated
* The primary reader is the author, secondary is client

For a large project (50 programmers):
* 2 years of work
* 500-page SRS
* purpose is build-to documents - must contain enough detail for all programmers and testers
* will use the SRS to estimate resource needs and plan development
* primary reader is managers, programmers & testers, secondary is clients, and senior management

### Authors

The SRS should fulfill the clients needs, not wishes.

### Exercises

1. The control shall provide status messages at regular intervals not less than every 1 minute.
    * The problem is that there is no upper bound for the regular intervals. Add a upper bound.
2. When the elevator is within 20 cm of the sensor's position, the sensor sends a high signal; otherwise a low signal.
    * We need to change this to a requirement (it's currently a implementation). 
    * The sensor should send a notification signal when the elevator .... 20 cm.
3. Charge numbers should be against the master list of corporate charge numbers, if possible.
    * We can *get rid* of if possible
    * It is also not complete. Then we need to is that a administrator/operator must be informed if the validation fails.

* Ambiguity
* Redundance
* Incomplete
* Inconsistent
* Not understandable

The above are very common problems with requirements. 

The slides have a full list of things to consider when writing an SRS.

## SRS Content

* Constraints -> Assumptions/standards
* External interfaces -> users, HW and other SW
* Functionalities -> Features
* Attributes (non-functionalities) -> considerations
* Performance

It should not include:

* Product development plans
* Assurance plans
* Product designs

Typical Mistakes:

* Noise
* Silence* - When you didn't properly describe something.
* Over-specifications
* Contradiction
* Ambiguity
* forward refernce
* wishful thinking

### Report to Operator

- In class example, will talk over on Friday