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

