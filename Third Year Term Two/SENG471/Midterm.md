# Software Requirements Engineering

There are five components of software engineering. They are listed below.

1. Requirements
2. Design
3. Developing
4. Testing
5. Maintaining/Deploying

When discussing the requirements of a system, you should be able to identify the:
* Desired capacities of the system
* Assumptions
* Constraints 
* Conditions

Requirements Engineering is a set of activities to identify and communicate the purpose of a software system and the contexts of which it will be used. Hence. RE acts as a bridge between the real world needs of the stakeholders affected by the software and the capabilities and opportunities afforded by software intensive technologies.

A reuqirement is a *condition* or *capability* that must be met by the system to solve a problem or achieve an objective.

There are four types of requirements:
* Enterprise Requirements
    * Sets the constraints/conditions (WHY)
* Functional Requirements
    * Features (WHAT)
* Non-Functional requirements
    * Constraints (HOW)
* Client/User Requirements
    * Constraints (WHO)

Requirements can also be divided in the WRPSM model. 

When writing requirements, try to have the following words: shall, should, must, have to, need to.

The WRSPM Model stands for Work, Requirements, Specifications, Program, and Machine.

In App Domain, you have Domain Properties - These are things you cannot change... your system must fulfill these. You also have Requirements, which are things you must fulfill to be able to do what's intended to do (to make client happy).

In Machine Domain, you have computers and programs and computers. 

The overlap of these two are the specifications, whih is behaviours that your system should be able to do (how the requirements are fulfilled).

What's the difference between verification vs validation?

Verification is done to ensure software meets specifications (verify it does what you want).
Validation is to check if the software covers everything (everything in the application domain)

The goal of Software Requirements Specification (SRS) is to:
* Contractual for development
* Baseline for evaluation
* Baseline for change control

The audience of the software requirements specification:
* Developers/programmers
* Project/Manager/Team Manager
* Clients
* Product owner and other business units

The extent of how in-depth a SRS is dependent on the scope of the project.

The SRS may be written by:
* The Software Engineer
* The procurer - (call for proposal, used to dictate the bid to propose)
* The bidders - (a proposal)
* The independent RE contracter

When evaluating a SRS - think to yourself.
* As a developer, can I code it?
* AS a tester, can I test it?

The SRS should be:
* Valid
* Unambiguous - Clear
* Complete 
* Understandable
* Consistent
* Ranked - Assign priority ranks for completion
* Verifiable - Makes the tester happy
* Modifiable
* Traceable

The following are the contents of a SRS:
* Constraints (assumptions/standards)
* External interfaces (users, HW, other SW)
* Functionalities
* Attributes (non-functionalities)
* Performance

It should not include:
* Product development plans
* Product assurance plans
* Product designs

Typical mistakes in a SRS:
* Noise - Irrelevant information
* Silence - nondescript feature
* Over-specification - solutions rather than the problem
* Contradiction - multiple incompatible definition
* ambiguity - at least two interpretations
* forward reference - term used prior its definition
* wishful thinking - features cannot be validated
* jigsaw puzzles - key info is scattered in a document
* Duckspeak requirements
* Unnecessary invention of terminology
* Inconsistent terminology
* Onus on the staff
* Writing for the hostile reader

We can evaluate a SRS using a truth table.

Formal inspection is a proven technique for reducing the number of defects in a program before it goes out the door. The greatest leverage from the time spent on software inspections comes from examining requirements documents.

We can perform the Fagan inspection to:
* Improve quality
* Have written output
* Provide major role in training junior staff

The benefits of the Fagan inspection
* Applications - more effective than testing
* Staff - recognition, morale, estimation, scheduling

This is the inspection process:
1. Planning
2. Overview
3. Preparation 
4. Inspection Meeting
5. Rework
6. Follow-up

During the planning stage, we need to select reviewers. Here are some possible reviewers:
* YOU
* Developer
* Tester/QA
* Other members
* Client/Customer
* Your boss

The people you don't want to review the document:
* Author
* The manager 
* People with conflict of interests with the author
* Friends of the author

Here are the roles of reviewers in a Fagan inspection:
* Moderator
    * The moderator is a competent programmer
    * Specically trained
    * From another project
* Designer/Author
    * Programmer who produced the design being inspected
* Coder/Implementor
    * Programmer responsible for translating the design into code
* Tester
    * Person responsible for writing/executing test cases

In a formal inspection, we have the following roles:
* Review leader
    * Chair the meeting
    * ensure the preparation
    * keep review focused
    * report the results
* recorder
    * keep track of the issues raised
* reader
    * summarize the product
* author
    * participate actively

The overview of the inspection objectives is to:
* partition the entire document into several parts
* ensure that the requirements are correct, feasible, necessary, unamibguous, verifiable, complete, consistent, modifiable, traceable

During the commencing moments of the inspection meeting, pleasure ensure:
1. Everyone is present.
2. Leader
    * Announces
    * Introduces
    * Explains
    * Reviews briefly
    * Checks
    * Explains

It is important that the review should not go ahead if the reviewers are missing, or if materials are not received, or the meeting is not properly prepared for.

There is four ways you can go about your inspection meeting.
* Checklist
    * Structured questions/issues
* Walkthrough
    * Step-by-step presentation, structured
* Round Robin
    * An issue/reviewers; in turn
* Speed Review
    * A chunk/reviewer for a short time

Following the inspection meeting, it is important to:
5. rework
5. Follow up

A feasbility study must also be conducted. The objective of a the feasbility study is to discover possibilities of a system and its alternatives. It provides information for management. It is important to note that a project at one point may not be feasible at a later point.

Organization of a system
* Finding the right person on the client's team to address the client's problem
* You can Google the organization of the system to figure out what's the role of the client within the corporation.
* What do the people we aren't talking to do?

Problems with the present system
* Identify the problem that the client has
* And identify what they're requesting... they probably won't line up
* it's your job to convince the client that they want your solution to the problem

Goals for the new system
* May reveal another issue deeper rooted that may may be derived from the first problem
* You need to be able to discover those

Contraints
* How much money does the client have?
* Engineering standards, environmental constraints

Possible alternatives
* What other solutions are there?

Here's some categories associated with the feasibility study.

Technical Feasibility
* Is the proposed technology practical?
* What kinds of technology will be needed?
* Is the required technology available "in house"?

Schedule Feasibility
* How long will it take to get the technical expertise?
* What are the schedule risk?
* What are the real constraints on project deadline?

Operational Feasibility
* How do client/users and maangers feel about this?
* Are there any resistances?

Economic Feasibility
* Purpose - what are the costs and benefits?
* Hardware/software?
* Management support?
* Alternative financing?

Difficulties
* Estimating benefits and costs
* Ranking multi-criteria alternatives

Calculating cost-benefit analysis
* The goal of cost-benefit analysis is to identify costs and benefits
* Determine cash flow
    * Project costs and benefits over time
    * Calculate Net Present Value (NPV) for all future costs/benefits
* Analyze cost-benefit
    * Break-Even point
    * Return on Investment (ROI)

The discount rate is the average annual return for investment in a company or an industry (reverse of interest rate).

Present Value = Current year $ value for cost/benefits in n years into the future. It's equal to 1/(1+i) ^n, where n is the years down the road.

Net Present Value is the total value of investment. NPV = (cumulative PV of all benefits) - (cumulative PV of all costs).

ROI (Return on Investment) = NPV/Cumulative PV of all costs

Next, we need to investigate Requirements Elicitation. Focus on the WHY. Focus on setting the WHY (decision tree) in Goal Analysis. You need to start by identifying your needs.

When doing goal modelling, here is the syntax:
* Soft goals are denoted by a cloud. They end up becoming non-functional requirements.
* Hard goals are ellipses. They end up being functional requirements.
* Help (+)
* Hurt (-)
* Make (++)
* Break (--)
* Order (->)
* AND (default), OR

Soft goals end up becoming on top, and hard goals on the bottom.

The Requirements Elicitation process involves the following
1. Establish Objectives
    * Business Goals
    * Problem to be solved
    * System Constraints
2. Understand Background
    * Organizational Structure
    * Application domain
    * Existing systems
3. Organize knowledge
    * Stakeholder identification
    * Goal prioritization
    * knowledge filtering
4. Collect Requirements
    * Stakeholder requirements
    * Domain requirements
    * Organizational requirements

Elicitation Requirements fall under several groups.

* Traditional
    * Introspection
    * Reading existing documents
    * Analyzing hard data
* Collaborative
    * Focus groups
    * Prototyping
    * Participatory design
* Contextual 
    * Ethnographic tech
    * Discourse analysis
    * Sociotechnical methods

In Traditional Introspection:
* Requirements analyst "imagines" what kind of system is required
    * This is a easy way to go about things
    * However, could be inaccurate - only based on the knowledge of your team
    * May be overconfident about what the information is
    * Stuff can change
* Background Reading
    * This includes reports, charts, manuals, descriptions, documents, etc.
    * This is good if you're making changes to existing system
    * THe current info may mismatch the existing info
* Analyzing hard data
    * You need to extrapolate the data given to you
* Interviews
    * It's good way to obtain opinions, get in-depth information
    * Problem is that it can be distrastrous if you come in unprepared
* Questionnaires
    * Good for large number of people
    * Too simple and gathers too list context
* Meetings
    * Use for feedback and summarization

In collaborative introspection:
* Focus groups
    * Brainstorming
    * Natural interaction
    * May be uncomfortable
    * May be subject to groupthink


When Scoping the Problem, we should consider the following:
* Who are the stakeholders?
* What are the problems?
* What are the alternatives
* What are the selection criteria
* What recommendation would you make?

When Modelling Requirements, we should consider:
* Guide elicitation
* Provide a measure
* Uncover problems
* Check understanding

There are different techniques associated with modelling:
* Modelling enterprises
    * Goals and objectives
    * Organizational structure
    * Tasks and dependencies
    * Agents, roles, intentionality
* Modelling information + behaviour
    * Information structure
    * Behavioral views
    * Timing/seqyence
* Modelling system qualities
    * all the 'ilities'


When drawing the diagrams (UML and BPMN), ensure that:
* Diagrams are from top-left to bottom-right
* Each activity has at least one transition in and one transition out