It is used in [[Dependency injection]].

`uses Java annotations for configuration of the bindings.`

- Two Guice modules are often used: **ProductionModule** and **TestModule**.
- Modules overwrite the `configure()` method to bind an implementation to a specification.

## Usage:
#### Production Module
![[Bildschirm­foto 2023-01-31 um 15.41.04.png]]![[Bildschirm­foto 2023-01-31 um 15.44.36.png]]

#### Test Module:
![[Bildschirm­foto 2023-01-31 um 15.51.32.png]]
![[Bildschirm­foto 2023-01-31 um 15.52.15.png]]

### The 4 Steps:
1. Tell Guice where to inject using the `@Inject` annotation:
	- Constructor injection.
	- Method injection.
	- Field injection (with Java Annotation)
```java
@Inject private Warehouse warehouse;
```
2. Create a Module to define the Binding:
```java
public class ProductionModule extends AbstractModule {
	public void configure() { 
		bind(Warehouse.class).to(WarehouseImpl.class); 
	} 
}
```
3. Instantiate an Injector and tell it which Module to use (i.e. provide a list of available bindings).
```java
Injector injector = Guice.createInjector(new ProductionModule());
```
Instantiate an instance of the class needing the injection (in our case: InventorySystem)
```java
InventorySystem inventorySystem = injector.getInstance(InventorySystem.class);
```


See more in [[Dependencies Injection using Guice]].