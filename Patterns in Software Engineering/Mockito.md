[[Mock object pattern]].

![[Bildschirm­foto 2023-01-29 um 20.32.14.png]]
![[Bildschirm­foto 2023-01-29 um 20.32.45.png]]

### Mock vs Spy:
1. mock()/@Mock: full mocking:
	- Optionally specify how it should behave via Answer/MockSettings.
	- when()/given() to specify how a mock should behave.
	- If the provided answers don’t fit your needs, write one yourself extending the Answer interface.
2. spy()/@Spy: 
	- partial mocking.
	- The behavior of single methods can be specified.
	- Real methods are invoked but still can be verified and stubbed

- In Mockito, a spy is a type of mock object that allows you to wrap an existing object and override its behavior partially. A spy is similar to a mock object, in that it can be used to verify the behavior of the system under test. The main difference between a spy and a mock is that, with a spy, you can delegate some method calls to the actual implementation, while with a mock, all method calls are stubbed and return default values.

- A spy can be useful in situations where you want to override the behavior of certain methods, while retaining the behavior of others. For example, you might want to use a spy to wrap an object that communicates with a database, and override the behavior of the methods that query the database, while retaining the behavior of the methods that update the database.

## Argument matcher
`If you are using argument matchers, all arguments have to be provided by matchers`.
- In testing frameworks like Mockito, an argument matcher is a special kind of matcher that is used to match the arguments passed to a method. Argument matchers are used to define flexible and reusable expectations for method calls. Instead of specifying exact argument values, you can use argument matchers to match based on certain conditions.

- For example, you might use an argument matcher to match any non-null argument, or to match an argument based on its type, or to match an argument based on a custom condition.
```java
List<String> mock = mock(List.class);

when(mock.get(anyInt())).thenReturn("hello");

// this call to the mock will return "hello"
assertEquals("hello", mock.get(0));

// this call to the mock will also return "hello"
assertEquals("hello", mock.get(1));
```
- In this example, we use the `anyInt()` argument matcher to match any `int` argument passed to the `get` method. The argument matcher `anyInt()` matches any `int` value, so the method call `mock.get(0)` and `mock.get(1)` both return "hello".
![[Bildschirm­foto 2023-01-29 um 20.41.37.png]]

### Inject mocks into SUT code
![[Bildschirm­foto 2023-01-29 um 20.44.09.png]]

### Argument captors:
Argument Captors are a feature of the Mockito testing framework that allow you to capture and verify the arguments passed to a mock object during a test.

With Argument Captors, you can define a `ArgumentCaptor` object and use it to capture the arguments passed to a mock during a test. You can then inspect the captured arguments after the test, and verify that they match the expected values.
![[Bildschirm­foto 2023-01-29 um 20.52.56.png]]

[[EasyMock vs. Mockito]].