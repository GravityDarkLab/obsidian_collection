1.  **Defining dependencies**: To define the dependencies of a class, you annotate its constructor or fields with the `@Inject` annotation. This tells Guice that these dependencies need to be injected.

```java
public class MyService {     
		private final PaymentService paymentService;    
		@Inject 
		public MyService(PaymentService paymentService) {
			this.paymentService = paymentService;
		}
}
```

2.  **Binding interfaces to implementation classes**: 
Next, you create a module that binds the interfaces to their implementation classes. This is done by calling the `bind()` method and passing in the interface type and the implementation type.

```java
public class PaymentModule extends AbstractModule {     
		@Override protected void configure() {
		    bind(PaymentService.class).to(PaypalPaymentService.class);     
		}     
	}
```

3.  **Creating the Injector**: To use the dependency injection, you create an `Injector` object by passing the module to it.
```java
Injector injector = Guice.createInjector(new PaymentModule());
```

4.  **Retrieving instances with dependencies injected**: To get an instance of a class with its dependencies injected, you use the `injector.getInstance(...)` method.
```java
MyService service = injector.getInstance(MyService.class);
```


> Guice will use reflection to inspect the constructors, fields, and methods of the class and inject the dependencies that were bound in the module.

> In addition to constructor injection, Guice also supports field injection and method injection, which allows injecting dependencies into fields and methods directly.

>Guice also allows to bind and inject instances, providers and constants. A provider is an object that can provide instances of a certain type, and can be used to create instances lazily or with additional logic.
 `bind(PaymentService.class).toProvider(PaypalPaymentServiceProvider.class);`

> Guice also allows to bind and inject instances, providers and constants. A provider is an object that can provide instances of a certain type, and can be used to create instances lazily or with additional logic.
 `bind(PaymentService.class).toProvider(PaypalPaymentServiceProvider.class);`
