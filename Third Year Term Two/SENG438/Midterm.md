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

In this slideset, we have learned that:
* Software errors/faults are inevitable 
* Software failure are expensive and sometimes life threatening
* Testing is a practical approach for finding faults to avoid failure
* The need for software testers and test engineers is growing fast
* We learn the basics of testing in this class

Validation involves acceptance test, usability testing, user feedback. Verification includes unit testing, integration testing, inspections, etc. Validation is checking whether the system meets customer's actual needs. Verification is whether the system is well-engineered, and bug free.

Software testing incorporates techniques to execute programs with the intent of finding as many defects as possible and/or gaining sufficient confidence in the SUT. A test case is a set of inputs and the expected outputs for a unit/module/system under test. A test suite is a set of test cases. Without the expected outputs, a test case is NOT complete.

Terminology:
* Direct input variable - a variable that controls the operation directly
* Indirect input variable - a variable that only influences the operations or its effects are propagated to the operations. By giving a test case a indirect input variable, you are specifying the context. 

Here are the types of test activities:
* Exploratory testing - design test values based on domain knowledge of the program and human knowledge of testing, explatory testing
* test-case design - design test values to satisfy coverage criteria or other engineering goal

Approaches:
* exploratory testing - tests are designed and executed at the samt time. Unscripted doesn't mean unprepared. It's about enabling choice, not constraining it.
* Scripted testing - tests are first designed and recorded. Then tehre may be secuted at some later time.

In exploratory testing, you use brain and fingers:
* create realistic scenarios that will cause software failure
* no strict plan

In manual scripted testing, follows a path that is written by tester/or someone else:
* the script includes test cases and test steps that are documented
* no deviation from the path laid out in the script

manual regression testing:
* regression testing is testing done to check that a system update does not reintroduce faults that have been corrected earlier
* usually performed after a bug fix code

Here are some facts about the Waterfall Model:
Pros:
* simple and easy to understand and use
* easy to manage due to rigidity of the model
* phases are processed and completed one at a time
* works well for smaller projects where requirements are well understood
* clearly defined stages
* easy to arrange tasks
* process and results are well documented

Cons:
* no working software is produced until late during the lifecycle
* high amounts of risk and uncertainty
* not a good model for complex and object-oriented projects
* does not allow for much reflection in revision

Iterative Model:
Pros:
* some working functionality can be developed quickly and early
* results are obtained early and periodically
* parallel development can be planned
* lest costly to change scope/requirements
* testing and debugging during smaller iteration is easy
* issues, challenges, and risks identified from each increment can be utilized/applied to the next increment
* during life cycle softawre is produced early which facilitates customer evaluation and feedback

cons:
* more resources required
* more management attention is required
* system architecture or design issues mayarise because not all requirements are gathered
* more complex

Testing in V-Model:
* Unit testing
    * testing of individual components
* integrationt testing
    * testing to expose problems arising from the combination of components
* system testing
    * testing the complete system prior to delivery
* acceptance testing
    * testing by users to check that the system satisfies requirements

V-Model:
Pros:
* highly disciplined model and phases are completed one at a time
* works for smaller projects 
* simple to use and easy to understand
* easy to manage due to the rigidity of the model

COns:
* High-risk and uncertainty
* Poor model for long and ongoing projects
* similar cons to waterfall

agile:
pros:
* is a realistic approach to software development
* functionality can be developed rapidly and demonstrated
* resource requirements are minimum 
* suitable for fixed or changing requirements
* delivers early solutions

Cons:
* you need an overall plan, an agile leader, and agile project manager
* strict delivery management dictates the scope, functionality, and adjustments
* high individual dependency since minimal documentation
* transfer of technology may be difficult due to lack of documentation

In test driven development, here are the steps:
1. add a test
2. run tests see new failure
3. write some code
4. run tests see all pass
5. refactor

Pros:
* TDD shortens the programming feedback loop
* guarantees the development of high quality code
* provides concrete evidence that software is working
* less debug time
* reduce software failure rate

cons: 
* programmers like to code, not test

Requirement analysis:
* test team studies the requirements from a testing point of view to identify the testable requirements
* The QA team may interact with various stakeholders (client, business analyst, technical leads, system architectrs) to understand the requirements in detail
* requirements could be functional or non functional
* autoamtion feasibility for the given testing project is also done in this stage

Activities:
* identify types of tests to be performed
* gather details about testing priorities and focus
* prepare requirement traceability matrix (RTM)
* identify test environment details where testing is supposed to be carried out

deliverables:
* RTM
* automation feasibility report

In a RTM, your requirements will be your columns, and the test cases will be your rows. Your job is to mark which requirements each test case fulfills.

The test plan:
* preparation of test plan/strategy document for arious types of testing
* test tool selection
* test cost/effort estimation
* resource planning and determining roles and responsibilities
* training requirement

deliverables:
* test plan/strategy document
* effort estimation

what to write in a test plan document:
* Introduction
* references
* test items (list the test items and their versions)
* features to be tested
* features not to be tested
* approach
* pass/fail criteria
* suspension criteria and resumption requirements
* deliverables
* test environment
* estimate
* schedule
* staffing and training needs
* responsibilities
* risks
* assumptions and dependencies
* approval

Test case development:
* this phase involves creation, verification, and rework of test cases and test scripts. test data, is identified/created and is reviewed then reworked.
* create test cases, automation scipts
* review and baseline test cases and scripts
* create test data

test environment setup:
* test environment decides the software and hardware conditions under which a work product is tested
* test environment setup is one of the critical aspects of testing

test execution:
* failure reports is a part of the deliverables

closure:
* testing team will meet, discuss and analyze testing artifacts to identify strategies that have to be implemented in the future
* document the learning out process
* prepare test metrics
* prepare analysis
* qualitative and quantitative reporting

unit testing:
* you can test functional and non-functional requirements

exhaustive testing:
* testing a possible inputs (practically impossible)
* partitioning techniques - exploratory testing, systematic (white box, blackbox)

Blackbox testing: unexpected functionality in the implementation that cannot be revealed by blackbox techniques
Whitebox testing: unexpected functioanlity in the specification that cannot be revealed in whitebox techniques

When performing unit test, consider the following:
* A unit test must only test only specific unit of functionality (class or method)
* It does not access a database
* Does not communicate via network
* Focus on development components
* Leave system before and after the same

* One sample from each equivalent class of input data
* Invalid data
* Boundaries

JUnit is a Java testing framework used to write and run tests.
* Assists with test execution automation
    * good for large scale testing
    * repeatable/automated test procedure
    * widely used in industry

Anatomy of JUnit testing:
1. Get the SUT
2. Create test case classes
3. Create test suite class
4. Create test runner class
5. Compile and run

A basic test case:
```Java
@Test
public void testAdd() {
    assertTrue("calc sum incorrect", 5==Calc.add(2,3));
}
```

Example of setup and tear down:
```Java

public class TournamentTest {
    Tournament tournament;

    @Before
    public void init() throws Exception {
        tournament = new Tournament(100,60);
    }

    @After
    public void destroy() throws Exception {
        tournament = null;
    }

    @Test
    public void testGetBestTeam() {
        Assert.assertNotNull(tournament);

        Team team = tournament.getBestTeam();
        Assert.assertNotNull(team);
        Assert.assertEquals(team.getName(), "Test1");
    }
}

```
To catch an exception, use the following:

```Java
@Test (expected = Exception.class)
```

A test fixture is the state of the test
* Objects and variables that are used by more than one test
* Initializations
* Reset values
* Different tests can use the objects without sharing the state
* objects used in test fixtures should be declared as instance variables

The following are `assert()` methods:

```Java
assertTrue("message", condition)
assertFalse("message", condition)
assertEquals(expected, actual)
assertSame(expectedm actual) // uses the == operator instead
assertNull("message", value)
```

It is important to note that a test case should not have a large number of assert statements. As soon as one fails, it stops.

Try to avoid logic like if, else, or try catch.

Sometimes you want to test a function multiple times with similar values. To avoid test code bloat, you can use parameterized tests. Use the following syntax:
```Java
@RunWith(Parameterized.class)
public class DataDrivenCalcTest {
    // insert test code here
}
```

1. Annotate test class with `@RunWith(Parameterized.class)` 
2. Create a public static method with `@Parameters` that returns a collection of objects as a test data set
3. Create a public constructor that takes in one row of data
4. Create an instance variable for each column of test data
5. Create your test cases using the instance variables

Stubs and mock objects are used to avoid dependencies.

1. A stub is a fake class that comes with a preprogrammed return value. It's injected into the class under test to give control over what's being tested as input. 
2. A mock is a fake class that replaces the depended class and can be examined after the test is finished.

Setting a mock object:
```Java
Mockery mockingContext = new Mockery();
values = mockingContext.mock(Valeus2D.class);
mockingContext.checking(new Expectations() {
    {
        one(values).getRowCount();
        will(returnValue(2));
        one(values).getValue(0,0);
        will(returnValue(7.5));
    }
})
```

For stubs:
```Java
Gradebook gradebook = mock(Gradebook.class);
when(gradebook.gradesFor(student)).thenReturn(grades(8,6,10));
```

In black box testing, we can do something called equivalence class partitioning.

Equivalence classes: partitions of the input space in such a way that input data have the same effect on the SUT
Completeness: Entire input set is covered
Disjoint: to avoid redundancy

Next, let's work with some decision tables.

Decision tables can help us deal with combination of inputs which produce different results. Basically, we can organize all the cases in the columns, the conditions on the rows, and decide if we need all the cases depending on the outputs they produce. The significance of this technique becomes clear as the number of conditions/inputs increases. The number of possible conditions is given by 2^n, where n is the number of inputs.

Next, let's look at combinatorial testing. The rationale behind combinatorial testing is that it may become impractical to test all possible combinations of values for all variables. The goal is to generate a subset of combinations and use them as test cases to achieve the same coverage of the system behaviour.

Profile-based testing is writing test for operations based on their frequency of usage.

Control flow structure: Sequence of execution of instructions of the program (execution of code lines). In a CFG, there are three types of nodes:
* Statement nodes: represent signle entry signle exit sequence of statements
* Predicate nodes: represent conditions for branching
* auxiliary nodes: for completing the graph

Here are some coverage metric examples:

* statement coverage = (number of statements exercised) / (total number of statements) * 100
* decision coverage = (number of decision outcomes exercised) / (total number of decision outcomes) * 100

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

## More Review

* Line Coverage is the number of lines that have been reached. 
* Decision/Branch coverage considers all the paths (if/else)
* Conditional coverage looks at each individual predicate and ensures that each variable reaches true/false

You can calculate cyclomatic complexity by doing 1 + d, where d is the number of predicate nodes.

Full path coverage means all edges going from the initial node to final node have been covered. 100% path coverage means 100% branch coverage.

MC/DC subsumes condition/decision coverage. COndition/decision coverage subsumes condition coverage and decision coverage. Decision coverage subsumes statement coverage.

* Du-pair - from the def to the use
* Du-path - paths starting from the initial def

Coverage:
* ADC - All-Defs coverage (Use every def)
* AUC - All-Uses coverage (get to every use)
* ADUPC - Follow all DU-Paths
