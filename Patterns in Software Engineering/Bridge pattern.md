It is a [[Structural Pattern]].


`must interface to several systems, some of them to be developed in the future, an early prototype must be demonstrated, must provide backward compatibility`.


- **Problem**: many design decisions are made final at design time or at compile time.
- **Solution**: the bridge pattern allows to delay the binding between an interface and its subclass to the startup time of the system.

The Bridge pattern is a structural pattern that separates an abstraction from its implementation so that the two can vary independently. The pattern consists of two parts: the abstraction, which defines the interface, and the implementation, which provides a specific implementation of the interface.
![[Bildschirm­foto 2023-01-23 um 22.45.29.png]]![[Bildschirm­foto 2023-01-23 um 22.46.33.png]]

## Key points
- Key points to consider when determining if the Bridge pattern is appropriate for a given situation:
	1.  **Separation of concerns:** The Bridge pattern is useful when you want to separate the concerns of an abstraction from its implementation, so that they can vary independently.
	2.  **Multiple implementations:** The Bridge pattern is useful when you want to provide multiple implementations of an abstraction without having to change the clients that use it.
	3.  **Changeability:** The Bridge pattern is useful when you want to be able to change the implementation of an object without affecting the clients that use it.
	4. **Flexibility:** The Bridge pattern increases the flexibility of the system by allowing the implementation to be changed at runtime, which can make the system more adaptable to changing requirements.
	5.  **Maintainability:** The Bridge pattern can make the code more maintainable, by making it easier to change the implementation of an object without affecting the clients that use it.
	6.  **Abstraction and implementation decoupling:** The Bridge pattern promotes the decoupling of the abstraction and implementation, by defining the abstraction through an interface or an abstract class and implementing it through concrete classes.


## Code Example:
```java
interface Renderer {
    public void renderCircle(float radius);
}

class VectorRenderer implements Renderer {
    public void renderCircle(float radius) {
        System.out.println("Drawing a circle of radius " + radius);
    }
}

class RasterRenderer implements Renderer {
    public void renderCircle(float radius) {
        System.out.println("Drawing pixels for a circle of radius " + radius);
    }
}

abstract class Shape {
    protected Renderer renderer;

    public Shape(Renderer renderer) {
        this.renderer = renderer;
    }

    public abstract void draw();
    public abstract void resize(float factor);
}

class Circle extends Shape {
    private float radius;

    public Circle(Renderer renderer, float radius) {
        super(renderer);
        this.radius = radius;
    }

    public void draw() {
        renderer.renderCircle(radius);
    }

    public void resize(float factor) {
        radius *= factor;
    }
}
```

