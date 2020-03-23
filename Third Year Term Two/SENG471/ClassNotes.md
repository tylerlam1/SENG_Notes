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

*The system shall report to the operator all faults that originate in critical functions or that occur during execution of a critical functions or that occur during execution of a critical seuqnece and for which there is no fault recovery response.*

- In class example, will talk over on Friday

FTFTFTTT

In this exam, the statement format is in the form (C1) OR (P1 AND P2)

The goal of software requirements engineering is to reduce ambiguity. 

## Organizing SRS

This is how you organize SRS:
* external stimulus 
* system feature
* system response
* external object
* user type
* mode 
* subsystem

## Domain Properties
a. Application domain
b. All interfaces (external) like hardware, other software, operated
c. Constraints
d. Requirements 

## Formal Inspection

* Software inspections and their cousins and reviews are proven techniques for reducing the number of defects in a program before it goes out the door.
* The greatest leverage from the time spent on software inspections comes from examining requirements documents

Walkthrough is a little bit faster than an inspection.

Steps:
1. Planning
2. Overview
3. Preparation
4. Inspection
5. Rework
6. Follow-Up

Possible Reviewers:
* YOU
* Developer
* Tester/QA
* Other members
* Client/Customer
* Your boss

## Feasibility Study

Imagine you are a Junior Engineering in Training. You just started in the company. Someone comes up to you to ask for help.

Or a senior comes up and gives you a piece of paper. 

The instructions are not clear as you would like. 

The goal of inspection is to point out the problem. i.e. you can break up sentences.

In a example: *The Apps should be downloaded in less than ten seconds on all kinds of computer devices.*
* Computer Devices is ambiguous
* What's the speed of the internet? The download time is dependent on the download speed 

But why feasibility study? 

Let's go back to the EIT example. The fact that your senior gave you a project means you can use this chance to learn about the company. The objective of the feasibility study is to determine the possibilities of a sytem and alternatives. This helps support your claim on whether you should pursue this project to management. In other words, it determines whether a project is feasible. Is there any backups?

In a feasibility study, your job is not to make a decision for your company. Rather, its used to provide information on what can happen, potentially alternatives, etc. All about the information. Like information about can the company afford it? is current technology available to do it?

There are different types:
* Technical - i.e. is the current technology up to date to complete this project
* operational - i.e. general resources/human resources
* Schedule - Does this fit inside the schedule
* Economic - Make a recommendation

### Computing Costs

* Costs
* APEGA website - salary survey results is published
* Salary: $25.00/hour + 20% benefits
    * Your co-workers may ask you to use $50.00/hour
    * This is because they need to cover overhead and other costs
* Contigencies

So when you're doing cost-benefit analysis:
* identify cost and benefits
    * tangible and intangible
    * one-time and recurring
* determine cash flow
    * project costs and benefits
    * calculate Net present value (NPV) for all future costs/benefits
* analyze cost-benefit
    * ROI - After break even point, how much can you gain from after investment
    * Break-even point - break even, as the name suggests

When calculating Net Present Value, let's investigate some terms:
* Discount Rate -  annual average return for investment
* PV = 1/(1+i)^n, where n = years down the road. 
* present value (PV) - current year $ value
*  Inflation rate - find on Bank of Canada website
* NPV - (cumulative PV of all benefits)
* Break-even = Yr. 4 + (beginning year mount)/ (endeyearamount + beginningyearamount)

For the in class example:
* 4 + (11262)/(13696 + 11262) = 4.45 years

To find the ROI:

* (NPV)/(Cumulative PV of all costs) = (13969)/(114217 + 3119) = 11.9%

## Stakeholders Goals

The objective of requirements engineering is to elicitate necessary information. Elictate is to find, to get. 

When doing Requirements Elicitation:
* Which problem needs to be solved? Boundaries
* Where is the problem? Application domain
* Whose problem is it? Stakeholders
* Why does it need solving? Stakeholders goal
* How might a software system help? Scenarios
* When does it need solving? Development constraints
* What might prevent from solving it? Feasibilities

Here's the approach:
* Focus on why systems are constructed
* Express the why as a set of stakeholder goals
* Use goal refinement to arrive at specific requirements
* Goal analysis
* Goal evolution
* Goal hierarchies

It's important to focus on *why* to derive goals:
* Advantages
* Disadvantages

Goals can change throughout time. 

In goal analysis, we need to consider the:
* Why - The high level goals
* How - Lower Level goals (operations)
* How else - alternatives

When modelling goals, we can use differnt types of notation:
* Hard goals - represented by a circle
* Soft goals - represented with a cloud
* Help (+)
* Hurt (-)
* Make (++)
* Break (--)
* Order (->)
* AND (default), OR

The objective is conflict resolution.

Soft goals become non-functional requirements (on top). Hard goals are functional requirements (bottom).

There are several tips regarding Stakeholders goals
* Use multiple scenarios
* Multiple perspectives

## Requirements Elicitation

You have sponsors, managers, users, stakeholders, software developers, and testers. They all play an important part in requirement elicitation. 

Sometimes, bias may come into play. Here are some examples of sources of bias:
* Social pressure, group think, impression management, wishful thinking, appropriation, misrepresentation, anchoring, inconsistency, availability, underestimation of uncertainty

The requirements elictation process is as follows:
1. Establish Objectives - Break your objective into what your need to achieve that objective. 
2. Understand Background - What problem needs to be solve? Constraints? 
3. Organize knowledge - How much do I know, how much do I not know? Goals Modelling .... etc
4. Collect Requirements - Elicitate. 

The first three bullets are pretty much background work, and need to be completed before the fourth bullet. 

The different types of Elicitation techniques:
* Traditional - Reading documents, analyzing data, interviews, etc.
* Contextual - Ethnographic technques, discourse analysis
* Collaborative 
* Cognitive

Traditional happens very often in the real world. It involves i.e. getting a document, and extrapolate from it. Basically, let them know which part can be reused and which cannot. Problems can come if you're copying old code to new code, and don't notice any differences (but there is). Other disadvantages is that it is missing requirements, or doesn't work. 

When doing background reading, could be reading manual books. Advantages is that it is straightforward (quick and easy) to do, but it takes a long time and boring. Disadvantages is that it could be different in the future than it is now. 

VAT = Value Added Tax 

## Interviews

* Keep it short
* You can uncover opinions, feelings, goals, hard facts
* Probe in depth
* State objectives in the beginning
* Watch out for answerable questions
* Interviewer's attitude
* Icebreakers

Questionnaires:
* Good for large amounts of people, remote administration
* Bad cause its simplistics, little context
* Watch for bias, with sample selection, appropriate questions, ambiguous questions

## Scoping the Question

Your goal is to avoid end up getting to a point where you design a software to do the requirements for you. You want the problem to be scoped effectively, and know all the problems.

Be sure to ask all the stakeholders.

First step, define the scope. Who is responsible for this particular project?
We also need to scope the solution. 

## Issues in Modelling Requirements

* Guide elicitation
* Provide a measure
* Uncover problems
* Check understanding

Model is an abstraction. It does not cover everything. It may not cover every aspect of a entity/relationship. Key point is that it should be good enough for your work. 90% is generally good enough.

Example 1:
* The customer receives the card, and then activates the card.
* The arrow is really important

## Notes on March 6th

Feasibility study is a good way to evaluate the information you have, and figure out which information you don't have. You can find out - which stakeholders may have the information I want?

Elicitation of information is automatically important - and is a objective of requirements engineering. Requirements Engineering is to elicit necessary information (was on the exam, and this was the answer - most students wrote all of the above).

Assume that after feasibility study, your clients are very happy. Next they come back, they choose an option. Your next plan of action is to:
* Model - functional and non-functional requirements. Enterprise Modelling - we have used BPMN so far (Business Process Modelling Notation). Inside each box of a BPMN is a verb. BPMN is a flow of activities to conduct a business. Each box represents an activity. 
    * An arrow indicates the flow.
    * You can separate them by pools.
    * You can also use UML Activity Diagram. For modelling business processes, UML *could* be used. This depends on how you use it. Most UML activity diagram is oriented to assist with coding - therefore, many details. However, the goal with enterprise modelling is to model the application model (thus extrapolate information in a way that everyone has same understanding). It's important not to have many details in the UML. 
    * BPMN dashed-line represents communication

Entity Relationship Diagrams are similar to UML, but not equivalent.
* Entity - nouns (any elicitated information becomes nouns). This makes your life easier.
* Relationship - connect something together (a verb to connect). i.e. Read, Write, observe. You have to have a verb to make a connecting thing. 
* Relationship in diamond, the box is entity (doesn't care if plural or singular)
* There is NO arrows in ERD. By default, we are already starting from left to right.
* Three entities connected to a relationship is known as a ternary relationship.
* Generalizations and specializations (partial and total)
* Top-down to confirm if generalization is correct. Bottom-up to ....

## Modelling

* Event is some kinds of actions (where something occurs)
* You should express requirements as constraints over states and requirements
* We can convert a BPMN diagram activity into a ER Diagram
    * i.e. a BPMN 'fly airplane' can be converted into a ER diagram with 'Pilot - flies - airplane'.
    * 'Pilot - engages - thrust'
* You can convert the ER to a requirements statement (specification)
    * When the airplane is in the air, the pilot should be prevented from accidentally engaging the reverse thrust

* SADT - Structured Analysis and Design Technique
* DFD - DataFlow Diagram
* ET - Event Trace (UML Sequence Diagram)

* In a SADT, for every data, you need to find every activity
* Data-activity duality - each data and activity will be together

* SADT and ET - usually about specifications
* BPMN, ER, SCR, are usually about requirements

* Different approaches
    * BP Diagram (UML activity diagram)
        * A business process for a target S/W system
    * ER Diagrams (UML class diagram)
        * Structural aspects of the target systems
    * SCR (UML statechart diagrams) 
        * Behavioural aspects of the target systems
    * SADT (DFD, UML use case)
        * Operational asepcts of the target system
    * ET diagrams (UML sequence diagrams)
        * Interactions among the structures of the target systems

