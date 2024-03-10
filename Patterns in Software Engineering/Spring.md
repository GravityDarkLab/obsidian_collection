It is used in [[Dependency injection]].

`uses Java annotations or XML to configure the binding of the specific subclass implementation to the interface.`

## Application context:
- Manages the objects of the application.
- Uses dependency injection to achieve inversion of control (IoC).
- The interfaces **BeanFactory** and **ApplicationContext** represent the Spring IoC container.
- **BeanFactory** provides basic functionalities for managing beans.
- **ApplicationContext** is a sub interface of **BeanFactory** and provides more enterprise specific functionalities.
- Resolve messages.
- Support internationalization.
- Publish events.
- Provide application layer specific contexts.

### Bean:
A `bean` in Spring is a single instance of an object managed by the Spring IoC (Inversion of Control) container. A bean is defined in the Spring configuration using either XML, Java annotations, or Java code. The bean definition includes information about the class, its dependencies, and its lifecycle.
![[Bildschirm­foto 2023-01-31 um 16.28.19.png]]
![[Bildschirm­foto 2023-01-31 um 16.29.15.png]]
![[Bildschirm­foto 2023-01-31 um 16.30.47.png]]

### Application Context:
The `Application Context` is the core of the Spring framework and is responsible for managing the lifecycle of the beans. It is an interface that represents the container and provides access to the beans and the services provided by the Spring framework. The Application Context is created by calling the `run` method of the `SpringApplication` class.
> When the Application Context is created, it reads the configuration information and instantiates, configures, and assembles the beans. **==The Application Context then manages the dependencies between the beans and provides a mechanism for resolving dependencies through either Constructor Injection, Setter Injection, or Field Injection==**.


## Which option should be preferred: constructor injection ?
- Leads to more robust code.
- All required dependencies are available at initialization time.
- Allows to identifying code smells.
	- Example: large number of arguments → problem: too many responsibilities.
- Simplifies writing unit tests.
- Prevents NullPointerExceptions and other errors.
- **Immutability**: 
	- once the framework creates a bean, it cannot alter its dependencies anymore.
	- Easier to debug.
	- Easier to use in multi-threaded environments

## Autowiring dependencies:
- Allows the Spring container to automatically resolve dependencies between collaborating beans by inspecting the beans that have been defined.
- There are 4 modes of autowiring a bean 
	1. **no**: the default value – this means no autowiring is used for the bean and we have to explicitly name the dependencies.
	2. **byName**: autowiring is done based on the name of the property, therefore Spring will look for a bean with the same name as the property that needs to be set 
	3. **byType**: similar to the byName autowiring, only based on the type of the property: this means Spring will look for a bean with the same type of the property to set (==if there's more than one bean of that type, the framework throws an exception==) 
	4. **constructor**: autowiring is done based on constructor arguments, meaning Spring will look for beans with the same type as the constructor arguments.
![[Bildschirm­foto 2023-01-31 um 16.35.22.png]]