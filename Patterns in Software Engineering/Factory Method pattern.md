It is a [[Creational patterns]].

The Factory pattern is a creational design pattern that provides a way to create objects without specifying the exact class of object that will be created. The Factory pattern defines a factory method, which is an abstract method that returns an object, and it's implemented by concrete factory classes.

The main idea behind the Factory pattern is to encapsulate the process of creating objects, so that the client code does not need to know about the specific classes of the objects that it creates. Instead, the client code only needs to know about the factory method and the interface of the objects that it creates.
![[Bildschirm­foto 2023-01-25 um 17.35.28.png]]

## Purpose of the factory class:
- Act as a delegate for the object creation.
- Allows the Client to use a single interface to the products of a factory.
- Polymorphism allows the client to use each of the concrete products in a uniform way.
- Makes it easy to add additional products.

## Checklist:
- If you have an inheritance hierarchy, consider adding a polymorphic creation capability by defining a factory method in the base class.
- Design the arguments to the factory method: 
	- what qualities or characteristics are necessary and sufficient to identify the correct derived class to instantiate?
- Consider designing an internal object pool that will allow objects to be reused instead of created from scratch (caching).
- Consider making all constructors private or protected


## Code example:

The client code can use the factory method to create objects, without knowing the specific classes of the objects that it creates. The factory method takes a string parameter that specifies the type of the object to be created.

Here's an example of how the client code can use the factory method:
```java
class FactoryPatternDemo {
    public static void main(String[] args) {
        ShapeFactory shapeFactory = new ShapeFactory();

        // get an object of Circle and call its draw method.
        Shape shape1 = shapeFactory.getShape("CIRCLE");
        shape1.draw();

        // get an object of Rectangle and call its draw method.
        Shape shape2 = shapeFactory.getShape("RECTANGLE");
        shape2.draw();
    }
}
```

See: [[Factory vs Abstract Factory]].