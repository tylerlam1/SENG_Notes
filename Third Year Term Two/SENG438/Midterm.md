# Software Testing

The objectives of software testing is:
* To understand the fundamentals of software testing, reliability, and quality
* Designing test cases and improving test suites
* Assessing reliability and quality of software

What affects quality?
* Quality
* Cost
* Time

The time is an important part as programmers need to meet the project deadline. In addition, the project needs to reach the market at the right time.

The cost is important because you need to meet the anticipated project costs.

The quality is important because the project needs to work for a designated period on the designated system.

Here is some terminology:
* Dependability is the ability of the system to avoid failures that are more frequent or more severe, and outage durations that are longer than is acceptable to the users. In other words, its the ability of a system to deliver service that can justifiably be trusted.

In software testing, there are several concepts that will be investigated:
* Exploratory 
* Black-box
* white-box
* Regression
* Unit-testing
* Integration testing

Different models will be covered:
* Coverage Model
* Adequacy Model
* Statistical Model

Processes:
* Test Process

With regards to software reliability, the following concepts will be learned:
* Reliability
* Availability
* Failure rate
* MTTF
* Failure density

The following models will be covered:
* Single failure model
* Multiple failure model
* relability growth model

The following processes will be investigated:
* SRE Process

When investigating software quality, the following concepts will be investigated:

* Predict size
* Predict effort
* Predict time

The following models will be investigated:
* ISO 9126
* ISO 25K

Assessment techniques:
* Pre-release
* Post-release

The definition of a service delivered by a system is its behaviour as it is perceived by its users; a user is another system that interacts with the former at the service interface. The function of a system is what the system is intended to do and is described by the functional specification. Correct service is delivered when the service implements the system function. The delivery of incorrect service is a system outage. A transition from incorrect service to correct service is service restoration.

* An error is a human action that results in software containing a fault
* A fault is a cause for either a failure of the program or an internal error. It must be detected and removed.
* Among the three factors only failure is observable.

Definition of a failure:
* A system failure is an event that occurs when the delivered service deviates from correct service. A failure is thus a transition from correct service to incorrect service.
* Any departure of system behaviour in execution from user needs. A failure is caused by a fault and the cause of the fault is usually a human error.
* A failure mode is the manner in which a fault occurs
* The failure efect is the consequence of a failure mode on the operation, function, status of a system/process environment.

The failure intensity is the rate failures are happening. For example, the number of failures per natural or time unit. Failure intensity is way of expressing system reliability. 

The failure density is the failure per KLOC (or per FP) or developed code.

Question: Is failure density a good metric for software quality? Answer: The more bugs found and fixed doesn't necessarily imply better software quality because the fault injection rate and the effort to fix them may be different.

Inspections are strict and close examinations conducted on the specifications, design, code, test, and other artifacts. Inspections allow for defect detection, prevention, and isolation. You start this early in the life cycle. On the contrary, testing allows for defect detection. It starts layer in life cycle. Typically, inspections are up to 20 times more efficient than testing. Code reading detects as many defects/hour as testing. 80% of development errors are usually found by inspections. Inspections resulted in a 10x reduction in cost of finding errors.

Despite that, inspection cannot replace testing. Testing is needed to identify complex interactions in large systems.

Definition of an error:
* A discrepancy between a computed, observed, or measured value or condition and the true, specified, or theoretically correct value or condition.
* A human action that results in software containing a fault

Here are some attributes of dependability:
* Availability: readiness for correct service
* Reliability: continuity of correct service
* Safety: absence of catastrophic consequences on the users and the environment
* Confidentiality: absence of unauthorized disclosure of information
* Integrity: absence of improper system state alterations
* maintainability: ability to undergo repairs and modifications

Dependability attribute smay be emphasized to a greater or lesser extent depending on the application. Availability is always required, whereas reliability, confidentiality, safety may or may not be required. Other dependability attributes can be defined as combinations or specializations of the six basic attributes.

When calculating availability, it is equal to the (uptime)/(uptime + downtime)

The following is the fault tolerance process:
1. Detection
2. Assessment
3. Recovery
4. Fault treatment and continued service

Fault removal:
* Fault removal is performed both during the development phase and during the operational life of the system
* Fault removal during the development phase of a system lifecycle consists of the three steps: verification-diagnosis-correction
* Verification is the process of checking whether the system adheres to the given propertiesm called the verification conditions. if it does not, the other two steps follow: diagnosing the faults that prevented the verification conditions from being fulfilled, and then performing the necessary corrections.
* After correcttion, the verification process should be repeated in order to check that the fault removal had no undesired consequences; the verification performed at this stage is usually called non-regression verification.
* Checking the specification is usually referred to as validation.
* Uncovering specification faults can happen at any stage of the development, either during the specification phase itself, or during subsequent phases when evidence is found that the system will not implement its function, or that the implementation cannot be achieved in a cost effective way.

Fault forecasting:
* Fault forecasting is conducted by performing an evaluation of the system behaviour with respect to fault occurrence or activation
* There are two aspects
    * Qualitative - which aims to identify, classify, rank the failure modes, or the event combinations that would lead to system failures
    * Quantitative - which aims to evaluate in terms of probabilities the extent to which some of the attributes of dependability are satisfied


# Inclass Midterm Review

Chapters:
1. Introduction
2. Foundations of testing
3. Unit testing - write unit tests using JUnit, SUT, write a program that includes our tests for SUT. Each class we have the before test, for, and after. Within each test, we have assertions for what we want to compare. We can compare two objects, two numbers, two strings, two arrays. The combination would comprise of your test suite. 
4. Black box - just look at the requirements, and try to write the test cases based on the requirements. 
5. White box - control flow
6. White box - data flow - we made flow graphs, paths, conditions on each branch, what is important. We also covered metrics like line, decision/branch coverage, and condition coverage. Data flow is the modified of control flow, adding where the data is defined and where it is used. 

In chapter 1, we had a lot of terminology available in the textbook. 

In JUnit (Chapter 3), we learned about mocks and stubs. We should be able to write mocks and stubs if needed. 

Chapter 4 was about black-box. It is equivalent to chapter 2 in textbook.

We test your knowledge on the midterm, as well as the tools in the lab. 

Samples questions:
* coverage criterion subsumes if every test set that satisfies C1 also satisfies C2.
* When do we need to use data-driven JUnit tests? When we want to write several test cases, but only the data changes.
* Boundaty value analysis is stronger than equivalence class testing because more interesting things happen at the boundary. 

Provide an example where the test covers 100% of statements but not 100% of decisions. Provide the test suite for decision coverage as well.

Sometimes he will give you code and fill in missing parts. You may also be instructed to write some test cases for a given coverage criterion.

Does testing prove the the correctness of the program? No guarantee the test suite can make the program work correctly. Testing can evaluate if the program is working okay, but can't prove its correct.

Is it possible to test a program completely? No. 

What is requirement traceability matrix (RTM)? Requirements in the black-box testing. In each row, we write the test case associated with the subset of those requirements. 

Difference between high severity/high priority? Priority is due to timing, severity is to due with the user/environment and surrounding. 

Decision coverage: Test cases for each decision
Condition coverage: Test each combination of each decision

Terms:
* Test plan - the functions you want to test and the techniques used to test them
* Failure - the thing that is observed
* Fault - the thing that causes the failure
* Failure rate - Failure/unit of time

Software testing is NOT a single activity
A failure causes a fault in a program F
A fault is caused by an error T
TDD is writing test and then implement the code T
Black-box testing tests the production code F
Smoke testing is a set of tests that aim that ensuring the most important functions work  T
MockingJay is NOT a mock framework (not gonna be tested)

By testing software before you release it, you're not can't guarantee software will work after release. You're just giving a 'best-effort' kind of thing.

Short solution

```Java
@Test
public void testLoginPage() {
    String expectedUsername = "hey"
    String expectedPassword = "buddy"
    assertEquals(expectedPassword, login.getPasswordFromUsername(expectedUsername));
}
```

1. Does (x, true, true, true) lead to 100% statement coverage? Convert it to a flow diagram and see.
2. No
3. Yes
4. 8