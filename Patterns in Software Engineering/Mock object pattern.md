It is a [[Testing patterns]].

The mock object pattern is a technique used in unit testing to create objects that simulate the behavior of real objects. These objects, called mock objects, are used to replace real objects in a test environment, allowing the test to focus on a specific aspect of the system being tested.

Mock objects are typically created using a mocking framework such as **EasyMock**, **Mockito**, or **jMock**. These frameworks provide tools for creating and configuring mock objects, as well as for verifying that the mock objects were used as expected.

> Based on the record and Play metaphore.

## Taxonomy:
- **System Model**.
- **System under Test (SUT)**: The SUT does not exist in isolation, it interacts with other participating objects in the system model that are not yet implemented called **==collaborators==**.
- **Test model**. (derived from the SUT).
- To be able to interact with collaborators, we add objects to the test model. These are called **==test doubles==**.
- **Dummy**: often used to fill parameter lists, passed around but never actually used.
- **Fake**: a working implementation that contains a “shortcut” which makes it not suitable for production code.
	- Example: a database stored in memory instead of on a disk.
- **Stub**: provides canned answers (e.g. always the same) to calls made during the test.
	- Example: random number generator that always return 3.14.
- **Mock**: mimic the behavior of the real object and know how to deal with a specific sequence of calls they are expected to receive.
![[Bildschirm­foto 2023-01-24 um 18.54.18.png]]


# EasyMock
go to [[EasyMock]].

# Mockito
go to [[Mockito]].

# Best practices:
- Use prefixes actual* and expected* •
- Use fixed data instead of randomized data.
- Write small and specific tests: do not extend tests to “just one more tiny thing”.
- Insert test data right in the test method.
- Favor composition over inheritance.
- Dumb tests are great: compare the output with hard coded values: do not reuse or rewrite production logic.