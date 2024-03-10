It is a [[Structural Pattern]].

- Problem: an existing component offers functionality, but is not compatible with the new system being developed.
- Solution: the adapter pattern connects incompatible components.
	- Allows the reuse of existing components.
	- Converts the interface of the existing component into another interface expected by the calling component.
	- Useful in interface engineering projects and in reengineering projects.
	- Often used to provide a new interface for a legacy system.
  → Also called wrapper

- The Adapter pattern is a structural pattern that allows incompatible objects to work together by providing an adapter that maps the interface of one object to the interface expected by the client. It can be used to convert the interface of an object to another interface that the client is expecting.

## Key points:
Here are some key points to consider when determining if the Adapter pattern is appropriate for a given situation:
1.  **Incompatible interfaces:** The Adapter pattern is useful when the interface of an object does not match the interface that the client is expecting.
2.  **Reusing existing code:** The Adapter pattern allows you to reuse existing code that cannot be used directly by the client because of incompatible interfaces.
3.  **Single Responsibility Principle:** The Adapter pattern can help to adhere to the Single Responsibility Principle by keeping the adapter class focused on adapting the interface of the object, and delegating the actual functionality to the adapted class.
4.  **Flexibility:** The Adapter pattern increases the flexibility of the system by allowing the reuse of existing code, and by making it possible to adapt the interface of an object to the interface that the client is expecting.
5.  **Decoupling:** The Adapter pattern promotes the decoupling of the client and the adapted object. The client only depends on the adapter, which in turn depends on the adapted object.

## Code example:
```java
interface Temperature {
    public double getTemperatureInCelsius();
}

class FahrenheitTemperature {
    private double temperature;

    public FahrenheitTemperature(double temperature) {
        this.temperature = temperature;
    }

    public double getTemperature() {
        return temperature;
    }

    public void setTemperature(double temperature) {
        this.temperature = temperature;
    }
}

class FahrenheitTemperatureAdapter implements Temperature {
    private FahrenheitTemperature temperature;

    public FahrenheitTemperatureAdapter(FahrenheitTemperature temperature) {
        this.temperature = temperature;
    }

    public double getTemperatureInCelsius() {
        return (temperature.getTemperature() - 32) * 5 / 9;
    }
}
```

> In this example, the `Temperature` interface defines the method for getting the temperature in Celsius. The `FahrenheitTemperature` class is a class that stores the temperature in Fahrenheit. However, the client code expects the temperature to be in Celsius. To allow the client code to use the `FahrenheitTemperature` class, the `FahrenheitTemperatureAdapter` class is used as an adapter that implements the `Temperature` interface and maps the `getTemperature` method of the `FahrenheitTemperature` class to the `getTemperatureInCelsius` method of the `Temperature` interface.