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


