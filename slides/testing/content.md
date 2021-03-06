# Testing

* Value of (Automated) Testing
* Test-Driven Development

note:
Before we talk about testing, since almost everyone here is involved in software,
let's talk about software real quick and its value.


## What is the value of software?

![working software](/slides/testing/working-software.jpg) <!-- .element width="60%" -->

note:
Is software itself inherently valuable?  Maybe.  Since, done right, it captures
the mental model of a problem and solution space so precise that a computer is able to understand
the instruction set and execute.
However, fundamentally, software is only valuable when it delivers user value, and therefore, business
value.
- If you are like me, I used to feel that the code itself is useful.
    - Clean design
    - Modular
    - Well-documented
    - Well-tested
- However, it's not the right perspective to view code.
- Code is actually risk.
- Every single line of code is a risk.
    - A financial risk: cost of maintenance, cost of change
    - A security risk: a larger attack surface
    - A business risk: code create bugs -> tarnish the company brand
    - A user risk: severe user harm from bugs such as financial institutions losing track of the user's money
        - Example: TSB bank botched upgrade, 3 weeks of system not being accessible, people's loans are not the right amount


## Business Value

![adding value](/slides/testing/adding-value.jpg) <!-- .element width="60%" -->

note:
So, if software is only valuable when it is bringing business value...


## Why do we test?

![software testing](/slides/testing/software-test.jpg) <!-- .element width="60%" -->

note:
On the surface, tt certainly does not seem to bring in business value.
Increase the cost of developing software.
- More people.
- Could take longer for software to get into production.
- Slows down delivery
- ask for contribution?


## We test in order

## to _increase confidence_

## for _stakeholders_

## through _evidence_

note:
To unpack
- Stakeholders = anyone that is affected by the software (users, business, developers, operations, legal)
- Increase confidence = being pragmatic, do things with balance.
- Evidence = takes creativity and ingenuity to come up with evidence for all the stakeholders.
So, we have established the goal of testing.


## Why automated testing?

![test automation](/slides/testing/test-automation.jpg) <!-- .element width="60%" -->

note:
Given that we've established the goal of testing.  Why do we want to automate testing?
- We want to automate testing because in order to maintain confidence in our software doing the right thing,
we need to test often, ideally very often.
- However, we know that humans are not very good at doing repetitive tasks well.  So, we offload that responsibility
to the machine.
**Question: Now, is it always necessary to do automate testing or testing in general?**


## Test (only) In Production! 

![roll back](/slides/testing/roll-back.jpeg) <!-- .element width="45%" -->
![analytics](/slides/testing/analytics.jpg) <!-- .element width="45%" -->

note:
- As the rule of internet headline goes, the answer to any headline question is "No".  How do you get away
with no automated testing? If we go back to gaining confidence that the software that's created works,
the best confidence to see that the software works is to validate it in production.
- Just let your users test! Right???
- Obviously, since you would be subject your users to potential buggy software, you would want to have
good monitoring systems and a good, quick rollback strategy.  Monitor system to detect
issues, and rollback strategy to fix the bugs.
- It also depends on what are the impacts on the users if there are issues.  If you are creating
financial software where you could cost your users millions of dollars due to bugs,
then it probably isn't a great idea to validate your software in production.
- However, if you are building a simple web app to display information, then it might be okay to validate
in production.


## To summarize

- Software should deliver business value.
- Tests increase confidence for the stakeholders through evidence.
- Automate away human error.
- Forgo testing with caution. 

---

## TDD / BDD

![test-driven development](/slides/testing/tdd.png) <!-- .element width="60%" -->

note:
Has anyone here never heard of test driven development?
One observation:
- almost everyone that I know always consider the "red" phase as the starting point
- define refactoring


## Brief History of TDD / BDD

![kent beck](/slides/testing/kent.jpg) <!-- .element width="30%" -->
![dan north](/slides/testing/dan-north.jpg) <!-- .element width="30%" -->


## Why do we do TDD?

- Deliver business value <!-- .element class="fragment" -->
- Clean code <!-- .element class="fragment" -->
- Refactor <!-- .element class="fragment" -->
- Confidence <!-- .element class="fragment" -->
- Tests <!-- .element class="fragment" -->
- Test-first <!-- .element class="fragment" -->


## Benefits of Test-First (TDD/BDD)

- Confidence in Functionality
- Simple Design
- Communication

note:
- Communication in pairs, between technical and non-technical stakeholders, etc.


## Q: What types of tests should I write?

note:
When I hear this question, I usually think of common, but not very useful testing pyramid.


## The Testing Pyramid

![testing pyramid](/slides/testing/testing-pyramid.jpg) <!-- .element width="45%" -->
![testing pyramid from cohn](/slides/testing/test-pyramid-cohn.png) <!-- .element width="45%" -->

note:
I mention useless because the most of the words are interpreted differently by different people.
Take "Unit" for example...


## Qualities of a Good Test Suite
- Confidence
- Clean
- Freedom to Refactor
- Fast

note:
Very hard to achieve all four at the same time, for all tests.
Fast vs Confidence (mocking)


## Q: What types of tests should I write?
### A: How is the quality of my test suite?

note:
The qualities of the test suite changes as the software system grows
- Early on, mostly integration issues. Test those integrations.
- As domain gets richer, introduce more class-level tests, component-level tests, etc.


## Example: Mocking / Test Doubles

note:
- One of the most common tool that we use are test doubles, lets look at how they affect the qualities of
the test suite?


## Test Doubles
- Dummy
- Stub (Read)
- Spy (Write)
- Mock
- Fake

note:
- Test doubles are standins for the real dependencies your software have.
- Inside out (detroit school) uses test doubles sparingly, decreases confidence,
only for scenarios that you cannot control (network).
- Outside in (london school) stubs, spies, and mocks extensively.


## Qualities of a Good Test Suite
- Confidence
- Clean
- Freedom to Refactor
- Fast

How do tests using extensive test doubles affect these qualities?

---

## Take Aways
- Tests provide evidence that increases stakeholder's confidence.
- Use TDD to deliver business value in the long-term.
- Evaluate tests against the qualities of the test suite.

note:
- It takes effort and creativity to collect the evidence for every kind of stakeholders.
- TDD is not sufficient to guarantee long-term business value delivery, but it is a crucial piece.
- It's not easy, but it does get easier as you do it more often.
- Evaluate the tests against the qualities, not the test pyramid.  Composition of the test suite
will always be changing as the software changes.
    - Including using test doubles.

---

# Q&A