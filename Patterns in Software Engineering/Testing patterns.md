## Introduction:
Testing is the process of evaluating a system or its component(s) with the intent to find whether it satisfies the specified requirements or not. In software development, testing is a crucial step in the software development life cycle (SDLC), where the quality of the software is validated. The main goal of testing is to identify any defects or bugs in the software, and to ensure that the software meets the requirements and expectations of the end-users.
- There are various types of testing, including:
	1.  Unit testing: This involves testing individual units or components of a software application.
	2.  Integration testing: This involves testing the integration of different components of a software application.
	3.  System testing: This involves testing the entire system, including all its components and sub-systems.
	4.  Acceptance testing: This involves testing the software to determine if it meets the end-user's acceptance criteria.
	5.  Performance testing: This involves testing the software's performance and scalability under different loads and conditions.
	6.  Security testing: This involves testing the software to identify any vulnerabilities or security risks.
## Purpose:
- The purpose of testing is the generation of failures.
- Two ways to express the success of testing a component:
	1. The test was successful because it did not generate a failure: The goal is to show the absence of failures.
	2. The test was successful because it generated a failure.

## Object oriented test modelling.
![[Bildschirm­foto 2023-01-29 um 20.24.47.png]]


## Patterns:
- Some common testing patterns include:
	1.  **[[Test Driven Development (TDD)]]**: This is a software development approach where tests are written first, and the code is written to pass those tests.
	2.  Behavior Driven Development (BDD): This is a software development approach where the behavior of the software is described in a natural language format, and tests are written to validate that behavior.
	3.  Page Object Model (POM): This is a design pattern for automating UI tests, where the UI elements of a web page are represented as objects, and test cases interact with those objects.
	4.  Test Automation Framework: This is a set of guidelines, tools, and best practices for automating the testing process.
	5.  [[Mock object pattern]]: This is a technique where mock objects or stubs are used to simulate the behavior of dependent components or services in a test environment.
	6.  Test Data Management: This involves managing the creation, maintenance, and disposal of test data in a way that supports efficient and effective testing.
	7. **[[Reflection test pattern]]**: used to test the internal compenents of classes (private attributes and methods).
	8. **[[Four stage testing pattern]]**: The Four-Stage Testing Pattern is a systematic approach to software testing that helps ensure that tests are thorough, reliable, and repeatable.
	9. **[[MVC testing patterns]]**.
	10. **[[Dependency injection]]**: The Dependency Injection Testing Pattern involves using DI to make it easier to test components in isolation.
	11. [[Testing a Client Server Application]].

## Modern Testing principles:
- Given, when, then logic:
	1. **Given (Input)**: test preparation like creating data or configure mocks (precondition).
	2. **When (Action)**: Call the method or action that you like to test.
	3. **Then (Output)**: Execute assertions to verify the correct output or behavior of the action (postcondition).
- Use Prefixes `actual*` and `expected*`.
- Use fixed data instead of randomized data.
- Write small and specific tests.
- Self contained tests.
	- Don´t hide the relevant parameters in helper function.
	- insert test data right in the test methode.
	- Favor composition over inheritance.
- Dumb tests are great: 
	- compare the output with hard coded values.
	- Don’t reuse production code.
	- Don’t rewrite production logic.
	- Don’t write too much logic.
- Don’t get the current timestamp by calling `Instant.now()` or `new Date()` in your production code:
	- The created timestamp cannot be controlled by the test, because it’s always different in every test execution.
	- Instead, use Java’s `Clock` class.
	- You can create a mock for the clock in tests, pass it to ProductDAO and configure the clock mock to return a fixed timestamp.
- Avoid assertTrue() and assertFalse().

![[Bildschirm­foto 2023-01-31 um 18.12.26.png]]
