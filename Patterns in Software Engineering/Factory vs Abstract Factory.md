The [[Factory Method pattern]] and the [[Abstract Factory pattern]] are both creational design patterns, but they have different purposes and use different mechanisms to create objects.

The [[Factory Method pattern]] defines an interface for creating an object, but lets subclasses decide which class to instantiate. **It provides a way to encapsulate object creation in a separate class, so that the client code does not need to know about the specific classes of the objects that it creates**. ==It allows subclasses to alter the type of objects that will be created==.

```java
interface Creator {
    public Product factoryMethod();
}

class ConcreteCreatorA implements Creator {
    @Override
    public Product factoryMethod() {
        return new ConcreteProductA();
    }
}

class ConcreteCreatorB implements Creator {
    @Override
    public Product factoryMethod() {
        return new ConcreteProductB();
    }
}
```

On the other hand, the [[Abstract Factory pattern]] provides an interface for **creating ==families== of related or dependent objects without specifying their concrete classes**. It provides a way to encapsulate the process of creating objects in a separate class, so that the client code does not need to know about the specific classes of the objects that it creates. It allows to create families of related objects and it's useful when you have a system with a lot of related objects that need to be created.![[Bildschirm­foto 2023-01-25 um 18.17.49.png]]

```java
interface AbstractFactory {
    public ProductA createProductA();
    public ProductB createProductB();
}

class ConcreteFactory1 implements AbstractFactory {
    @Override
    public ProductA createProductA() {
        return new ProductA1();
    }
    @Override
    public ProductB createProductB() {
        return new ProductB1();
    }
}

class ConcreteFactory2 implements AbstractFactory {
    @Override
    public ProductA createProductA() {
        return new ProductA2();
    }
    @Override
    public ProductB createProductB() {
        return new ProductB2();
    }
}
```
