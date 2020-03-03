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