# Software Testing

The goal of this class is to understand software testing and reliability engineering processes. You also want to design test cases and improve test suites, and assess reliability and quality of software.

In this class, it's important to mix theory and practice together. Theory/Research/Concepts are focused on during lectures and exams. Labs and projects will be emphasized in labs and projects.

## What affects Software Quality?

A couple factors affect software quality.
* Time - Meeting the project deadline, or reaching the market at the right time
* Cost - Meeting the anticipated project costs
* Quality - Working fine for the designated period on the designated system

Let's look at some terminology.

The dependability of a system is the ability to avoid failures that are more frequent or more severe, and outage durations that are longer, than is acceptable to users.

The dependability is dependent on the threats, attributes (availability, reliability), means, and models.

## Software Testing

Software Testing can be exploratory testing, white-box, black-box, regression testing. 

To calculate Reliability = exp(-xt)

x = failure rate/ failure density
t = time

x = 1/(Mean time to failure)

## Software Reliability

Software Reliability involves the Reliability, Availability, Failure Rate, MTTF,Failure Density.

## Software Quality

Software Quality involves size and effort (predict size, predict effort, predict time).

## Service

A service delivered by a system is its behaviour as its perceived ny its users. A user is another system that interacts with the former at the service interface.

The function of a system is what the system is intended to do, and is described by the functional specification.

## Dependability: Threats

An error is a human action that results in software containing a fault.
A fault is a cause for either a failure of the program or an internal error.

A failure is an event that occurs when the delivered service deviates from the correct service.

The failure intensity is the number of failures per natural or time unit.

When considering testing vs inspection:
* Inspections are strict and close examinations conducted on specifications, design, code, test and other artifacts.

You can start inspections early in the life cycle.

* Testing on the other hand, allows for defect detection and starts later in the lifecycle.

Inspection cannot replace testing. Inspections can only replace testing if all information gleaned through testing could be obtained through inspection.

## Errors

When considering errors, there are two meanings:
* A discrepancy between a computed, observed or measured value and the true, specified, or theoretically correct value

* Human errors are hardest to detect

## Dependability: Attributes

* Availability: readiness for correct service
* reliability: continuity for correct service
* safety: absence of catastrophic consequences on the users and the environment
* confidentiality: absence of unauthorized disclosure of information
* Integrity: absence of improper system state alterations
* Maintainability: ability to undergo repairs and modifications



## JUNIT

When doing test execution, you need to use mocking. You are free to choose your mocking framework. Example of jMock tests for the SUT of the Assignment 2 will be given. 

Unit testing itself is quite simple. The goal is to separate unit under test from the rest of the system, and test that. Imagine you want to test add(x,y). 
1. Create a program that calls SUT.
2. Executes it with the setup value of its arguments and spits out the execution result.
3. Compare output with expected value.

Problem is that it is not very extendible, and quite difficult to manage it in a larger environment. 

The scope: Ensure that each unit has been implemented correctly.
* Looking for problems in isolation

When unit testing, focus on developed components and surroundings, invalid data, boundaries, and one sample from each equivalent class of input data.

### Terminology:
* Test Drivers: Modules that act as temporary replacement for a calling module and give the same output as that of actual product
* Test execution: The execution of an individual unit test
* Test case: A test case is the most elemental class.
* Test suites: A test suite is a set of tests that all share the same fixture.
* Assertion: An assertion is a function or macro that verifies the behaviour of a unit under test.

### Anatomy
1. Get the SUT
2. Get the test case classes
3. Create test suite class
4. Create test runner class
5. Compile and run

## Mocks and Stubs

Sometimes SUTs have dependencies (recall UML). Unit tests should not have dependencies. When testing collaborative units together, use integration test, feature test.

A stub is a fake class that coomes with preprogrammed return values. It's injected into the class under test to give control over being what's tested. A stub is often and-coded in the implementation language, i.e. no need to use a mock framework but it is okay to use one.

Steps:
* Setup - Prepare SUT that is being tested and its stubs collaborators
* Exercises - Test the functionality
* Verify State - Use asserts to check object's state
* Teardown - Clean up resources

A mock object is a fake object that devices whether a unit test has passed or failed by watching interactions between objects.

We need a mock object when a unit of code depends on an external object. A mock framework example would be jMock, Mockito, PowerMocks, EasyMock, etc.

Let's compare a mock and a stub.

A stub gives out data that goes to the object/class under test. The unit test directly asserts against class under test, to make sure it gives the right result when fed this data.

A mock is created and waits to be called by the class under test. It makes sure it is contacted in exactly the right way.

To test Lifecycle with Mocks:
* Setup data - prepare object that is being tested
* Setup expectation - Prepare expectations in mock that is being used by primary object
* Exercise - Test the functionality
* Verify expectations - Verify that correct methods has been invoked in mock
* Verify state - Use asserts to check object's state
* Teardown - Clean up resources

## Quick Review

Blackbox testing applies to all granularity levels. 

### Testing

Equivalence class partitioning is when inputs in an equivalence class are assumed to be treated the same by the system. 

When doing Equivalence Class Testing (ECT), you divide input set into a partition that can be considered the same. 
* Equivalence Class - partition of the input space in such a way that input data have the *same effect* on the SUT.
* Completeness - Entire input set is covered
* Disjoint classes - to avoid redundancy
* Equivalence classes must be chosen wisely.
* guessing the likely system behaviour is needed.

A group of test cases are "equivalent" if:
* They all test the same unit
* If one test case can catch a bug, the others will probably do
* If one test case does not catch the bug, the others probably do.
* They all invoke the same input variables
* They all affect the same output.

The entire set of inputs can be divided into two subsets:
* one containing all the expected or legal inputs
* the other containing all unexpected inputs

There's different types of ECT, like strong and weak ECT.

## Boundary Value Testing

While equivalence partitioning selects tests from within equivalence classes, boundary value analysis focuses ont ets at and near the boundaries of the equivalence classes. Tests derived may overlap.

Hints:
* Check if the boundary conditions for variables are set correctly
* Check if the inequality boundary conditions can be changed to equality or not
* Check if the counter variables allow departure from loop or not

## Decision Tables

* Can help us deal with combination of inputs which produce different results
* Has conditions, and necessary actions (result of what we expect). Each column is a test case.

* Decision tables help us visualize test suites.
* Ideal for describing situations in which the number of combinations of actions are taken under varying conditions.

## Mutation Testing

A way of fault-based testing is Mutation Testing.

* One advantage of coverage criteria is that they can be measured automatically.
* To control testing progress towards completeness.
* High coverage is not a guarantee of fault-free software, just an element of information to increase confidence.

The obvious metric is to count the cumulative number of failures found so far.

* Coverage-based (BB, WB testing)
    * Rationale: the better test suite covers more from specification/code/data
* Fault-based (mutation testing)
    * Rationale: the better test suite detects more faults

* Mutation: bug injection
* Mutation testing: finding injected bugs

Fault-based testing directs more typical faults that could occur in a program. Syntactic variations are applied in a systematic way to the program to create faulty versions that exhibit different behavior. Mutation testing helps create effective test data in an interactive manner. In fault-based testing, we intentionally inject a fault (change + to -) and run our test suite to see if it can detect the injected faults.

Terms:

* Surviving means changing the source code did not change the test result
    * Thats bad.
* Killed means changing the source code changed the test results.

Different types of mutants:
* Stillborn mutations: syntactically incorrect, killed by compiler
* trivial mutants: killed by almost any test case
* equivalent mutant: always acts in the same behavior as the original program

The above cases are not interesting from a mutation testing perspective. Only those mutants are interesting which behave differently than the original program, and we do not have test cases to identify them.

To automate the generation of mutants, we use *mutation operators* that is predefined program modification rules.
1. Change operator

## GUI Testing

* GUI testing is the process of testing a product that uses a graphical user interface

The problem with manual testing is that:
* Not very repeatable
    * Either cannot remember exactly how it eas last tested
    * Or too expensive to document detailed procedures
* Very effort intensive

The benefit of automated testing:
* It gives us rapid feedback
* It is repeatable and reusable
* Much faster than human testers, but needs up-front investment
* Automated tests and TDD can potentially drive design
* It is better documented

Event if we conduct API-based black box and coverage-based white box testing, the SUT can have defects in the GUI logic (code) and the glue code.
* The GUI is a type of user interface item that allows people to interact with programs in more ways than typing
* GUI software is an event-driven software
* User events (like clicks) trigger event handlers

* Event driven nature of GUIs leads to many challenges in testing them
* The user has extremely wide choice of actions compared to BB/WB testing
* Because users many click on any pixel on the screen, there are many more possible user inputs that can occur

There are different approaches to GUI testing:
* Completely manual (lab 1)
* Semi-automated generation (lab 4)
* Automated generation (based on execution of user sessions using a GUI model)

The manual approach is done by manually stepping through pages of test procedures or by exploratory testing. The capture/playback approach captures user sessions (user inputs and events) and stores them in scripts (one per session) suitable to be used to replay the user session.
In order to do this, we need:
* A tool that can capture
* SUT
* A tool that can replay

Process:
1. A tester interacts with the system GUI to run the system, thus generating sessions of sequence of mouse clicks, UI and keyboard events, voice commands, etc.
2. the tool captures and stores the user events and the GUI screenshots
3. the tesrer can replay the execution by running the script
4. in case of GUI changes, the script must be updated

The challenge with capture/playback tools is that when the GUI changes, input sequences previously recorded may no longer be valid.

## Software Reliability Engineering
Now we have learned techniques of blackbox, whitebox, GUI, etc types of testing. All these types of testing have a main goal of testing a particular unit (unit testing). We now will focus more on integration, system, and acceptance testing. This is a focus on quality.

Here are things to consider:
* How to build quality into a software project?
* How to manage quality as we go forward with software development?
* How to measure quality of software in the end?
* Decision making process and plan for release and post-release activities.

Validation: Checking whether the system meets customer's actual needs
Verification: Whether the system is well-engineered, bug free.

So what exactly is software quality?
* Conformance to requirement
    * The requirements are clearly stated and the product must conform to it
    * Any deviation from the requirements is regarded as a defect
    * A good quality product contains fewer defects
* Fitness for use
    * Fit to user expectations: Meet user's needs
    * A good quality product provides better user satisfaction

When building software, maintenance is responsible for about 60% of total cost for a typical software product. Therefore, to build quality into a system, it means:
* Establishing *Software Quality Assurance (SQA)* programs
* Establishing *Reliability Engineering (SRE)* process

### Reliability Theory
* Reliability Theory developed apart from the mainstream of probability and statistics, and was used primarily as a tool to help nineteenth century maritime and life insurance companies compute profitable rates to charge their customers. Even today, the terms "failure rate" and "hazard rate" are often used interchangeably.
* Probability of survival of merchandise after one MTTF is R = e^-1 = 0.37.

You can think of the 'Bathub curve' we learned in ENCM 511 as the typical lifecycle of a piece of hardware. The failure rate for a 'burn in' is high because you're trying to still figure out how to get it working, and in the useful life is becomes stable, and the 'wear out' period is where the device begins to start failing again. 

Unlike hardware, software reliability doesn't decrease with time. Hardware faults are mostly physical faults, and software faults are mostly design faults. 

Software Reliability Engineering is a multi-faceted discipline covering the software product lifecycle. It involves both technical and management activities in three basic areas. 
* Software Development and Maintenance
* Measurement and Analysis of reliability data
* Feedback of reliability information

SRE is a practice for quantitatively planning and guiding software development and test, with emphasis on reliability and availability. It simultaneously does three things:
* It ensures that product reliability and availability meet user needs
* It delivers the product to the market faster
* It increases productivity, lowering product life-cycle cost

In applying SRE, one can vary relative emphasis placed on these three factors.

There are five steps in the SRE process:
* Define necessary reliability
* Develop operational profiles
* Prepare for test
* Execute test
* Apply failure data to guide decisions

## System Reliability

The *reliability block diagram* is a graphical representation of how the components of a system are connected from a reliability point of view. Reliability of the system is derived in terms of the reliabilities of its individual components. The most common configurations of an RBD are the serial and parallel configurations. A system is usually composed of combinations of serial and parallel configuration. RBD analysis is essential for determining reliability, availability, and down time of the system.

In a serial system configuration, the elements must all work the system to work and the system fails if one of the components fail. THe overall reliability of the serial system is lower than the reliability of its individual components.

In a parallel system configuration, the components are considered to be redundant and the system will cease to work if all the parallel components fail. The overall reliability of the system is higher than its individual components.

In RBD:
1. Define boundary of the system for analysis
2. Break system down into functional units
3. Determine serial-parallel configurations
4. Represent each component as a separate block in the diagram
5. Draw lines connecting the blocks in a logical order for mission success

In serial system reliability:
* No redundancy
* All component of the system are needed to make the ssytem function properly
* If any sone of the component fails, the system fails

The serial system reliability can be calculated from component reliabilities, if the components fail independently from each other. To find the system reliability, you multiple them together.

In parallel system reliability:
* System with redundancy
* Only ONE out of n (identical) components is needed to make the system function properly
* If ALL of the components fail, the system fails.

You can calculate the reliability from 1- sum(1-reliability_per_component). 

In sequential systems, when one component fails, the next one is assigned to fulfill the job. This is done in sequence until no components left. If ALL components fail, the system fails. You can also combine parallel-series configurations.