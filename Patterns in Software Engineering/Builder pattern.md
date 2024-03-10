It is a [[Creational patterns]].

`Builder often builds a composite`

The Builder pattern is a creational design pattern that provides a way to create complex objects by using a step-by-step approach. It separates the construction of a complex object from its representation, so that the same construction process **can create different representations**.

The Builder pattern defines a `Builder` interface, which specifies the methods that are required to build the complex object. The concrete builders implement the `Builder` interface and provide the implementation for these methods. The `Director` class is responsible for using the builder to construct the complex object.
![[Bildschirm­foto 2023-01-25 um 18.40.49.png]]
## Code example:
```java
class Computer {
    // fields for computer parts
    private String CPU;
    private String GPU;
    private int RAM;
    private int storage;

    public void setCPU(String CPU) {
        this.CPU = CPU;
    }

    public void setGPU(String GPU) {
        this.GPU = GPU;
    }

    public void setRAM(int RAM) {
        this.RAM = RAM;
    }

    public void setStorage(int storage) {
        this.storage = storage;
    }

    // other methods
}

abstract class ComputerBuilder {
    protected Computer computer;

    public Computer getComputer() {
        return computer;
    }

    public abstract void buildCPU();
    public abstract void buildGPU();
    public abstract void buildRAM();
    public abstract void buildStorage();
}

class GamingComputerBuilder extends ComputerBuilder {
    public GamingComputerBuilder() {
        computer = new Computer();
    }

    @Override
    public void buildCPU() {
        computer.setCPU("i7 9700k");
    }

    @Override
    public void buildGPU() {
        computer.setGPU("RTX 3080");
    }

    @Override
    public void buildRAM() {
        computer.setRAM(32);
    }

    @Override
    public void buildStorage() {
        computer.setStorage(1000);
    }
}

class Director {
    private ComputerBuilder builder;

    public Director(ComputerBuilder builder) {
        this.builder = builder;
    }

    public void constructComputer() {
        builder.buildCPU();
        builder.buildGPU();
        builder.buildRAM();
        builder.buildStorage();
    }
}
```
Here's how the client code can use the `Director` class and `GamingComputerBuilder` class to create a gaming computer:
```java
ComputerBuilder builder = new GamingComputerBuilder();
Director director = new Director(builder);
director.constructComputer();
Computer computer = builder.getComputer();
```
In this example, the client code uses the Director class to construct a computer using the GamingComputerBuilder. By using this pattern we can create different representations of the computer object by using different builders and the same construction process.