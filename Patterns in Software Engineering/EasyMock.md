[[Mock object pattern]].

![[Bildschirm­foto 2023-01-24 um 18.53.52.png]]

### MockTypes
- "Nice" mocks, also known as "loose" mocks, are mocks that do not enforce strict behavior verification. In other words, the mock object does not validate that the methods were called in a specific order or with specific arguments. The goal of a "nice" mock is to verify that a method was called, without verifying how many times it was called or with what arguments.
> **==Allows all method calls and returns appropriate empty values (0, null, or false)==**.

- "Strict" mocks, on the other hand, enforce strict behavior verification. The mock object validates that the methods were called in a **==specific order==**, with specific arguments, and with a specific number of invocations. The goal of a "strict" mock is to **==verify the exact interactions between the test subject and its dependencies==**.

> The choice between "nice" and "strict" mocks depends on the specific testing scenario and the desired level of validation. "Nice" mocks are typically used when you want to verify that a certain method was called, without verifying the exact details of how it was called. "Strict" mocks are typically used when you want to verify the exact interactions between the test subject and its dependencies.

### Code example:
![[Bildschirm­foto 2023-01-24 um 18.54.39.png]]


[[EasyMock vs. Mockito]].