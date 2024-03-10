- The Command pattern is a behavioral design pattern that encapsulates a request as an object, allowing for a separation of the command execution from the object that invokes the command. The pattern is used to represent an action or a set of actions that can be executed, undone, and redone.

- A common example of the Command pattern is a remote control with multiple buttons, each button represents a different command, such as turning on or off a TV, adjusting the volume, or changing the channel. Each button press invokes a different command, and the command is responsible for executing the corresponding action on the TV.

![[Bildschirm­foto 2023-01-24 um 22.11.45.png]]

## Steps:
5 steps to realize a command pattern:
1. Create the Command interface:
	- The key to the pattern: declares the interface for executing operations, includes an abstract operation execute() 
2. Create the Concrete Command classes (control objects):
	- Each concrete class specifies a receiver-action pair by storing the receiver as an instance variable and provides a different implementation of the execute() method to invoke the specific request 
3. Create the Receiver (entity objects):
	- Has the knowledge to carry out the specific request 
4. Create the Invoker (boundary objects) 
5. Create the Client
![[Bildschirm­foto 2023-01-24 um 22.13.52.png]]

## Code example:
```java
interface Command {
    void execute();
}

class Light {
    public void turnOn() {
        System.out.println("Light turned on");
    }

    public void turnOff() {
        System.out.println("Light turned off");
    }
}

class LightOnCommand implements Command {
    private Light light;

    public LightOnCommand(Light light) {
        this.light = light;
    }

    public void execute() {
        light.turnOn();
    }
}

class LightOffCommand implements Command {
    private Light light;

    public LightOffCommand(Light light) {
        this.light = light;
    }

    public void execute() {
        light.turnOff();
    }
}

class RemoteControl {
    private Command command;

    public void setCommand(Command command) {
        this.command = command;
    }

    public void pressButton() {
        command.execute();
    }
}
```
This example demonstrates how the Command pattern can be used to encapsulate a request as an object, allowing for a separation of the command execution from the object that invokes the command. It also allows for easy extension of the system by adding new commands without modifying the existing classes.

## Benefits:
- Complexity reduction: 
	- Decouples boundary objects from control objects and separates them from entity objects
	- **Example**: 
		- boundary objects are the menu items and buttons.
		- They send messages to the control objects (the ConcreteCommands).
		- Only ConcreteCommand objects can modify entity objects (the receivers)
- Dealing with change:
	- When the user interface is changed, only the boundary objects need to be modified. 
	- The code for the control and entity objects does not have to be touched.
	- **Examples**:
		- A menu item is added.
		- The menu is replaced by a palette.
		- The menu is replaced by a speech recognition system