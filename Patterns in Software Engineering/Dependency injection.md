It is a [[Testing patterns]].

`Goal: reduce the high coupling as much as possible.`
`A dependency injection framework reduces the coupling for the Client .`

Dependency Injection (DI) is a design pattern that allows components to receive their dependencies from external sources rather than creating them internally. This helps to make the code more flexible and modular, as components can be easily swapped or replaced with different implementations without affecting the rest of the system.

> This is achieved by injecting mock implementations of dependencies into the components during testing, rather than using the real implementations. This makes it possible to control the behavior of the dependencies and validate the behavior of the components under test.

- Binding (the selection of the correct subclass to be instantiated for a certain interface) is done by the dependency injection framework.
- There are no compile time dependencies between Client and implementation classes anymore.
- Because there is no factory, the Client class can be reused more easily
![[Bildschirm­foto 2023-01-31 um 15.35.54.png]]



> In Java, there are several frameworks that can be used to implement DI, including [[Guice]] and [[Spring]]. These frameworks provide a convenient way to manage dependencies and inject them into components, making it easy to test components in isolation.



## Inversion of control:
- Control of objects or portions of a program is transferred to a container or framework.
- The framework takes control of the flow of a program and makes calls to the program’s custom code.
- To enable this, frameworks use abstractions with additional behavior built in.
- If you want to add your own behavior, you need to extend the classes of the framework or plugin your own classes.

### Advantages:
- Decoupling the execution of a task from its implementation.
- Making it easier to switch between different implementations.
- Greater modularity of a program.
- Greater ease in testing a program by isolating a component or mocking its dependencies and allowing components to communicate through contracts.