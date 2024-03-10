It is a [[Behavioral patterns]].

The Template Method pattern is a behavioral design pattern that defines the skeleton of an algorithm in a method, and allows subclasses to fill in the details. The pattern is used to define a base class that provides a standard way of executing a certain algorithm, and allows subclasses to customize or override certain steps of the algorithm without changing the overall structure of the algorithm.

A common example of the Template Method pattern is a simple game framework, where the base class defines the basic structure of a game loop, such as handling input, updating game logic, and rendering the game, and allows subclasses to provide the specific implementation of each step.

- A framework is normally more complex:
	- Includes control flow.
	- Includes predefined white spots that application developers should implement.
	- Defines a skeleton where the application implements its own features to fill this skeleton.
	- Calls application code when appropriately.
	- **Benefit**: 
		- Developers do not need to worry if a design is good or not, but just about implementing domain specific functions.
	![[Bildschirm­foto 2023-01-24 um 20.54.18.png]]


## Example code:
```java
abstract class Game {
    public final void play() {
        initialize();
        startPlay();
        endPlay();
    }
    protected abstract void initialize();
    protected abstract void startPlay();
    protected abstract void endPlay();
}

class Cricket extends Game {
    @Override
    protected void initialize() {
        System.out.println("Cricket Game Initialized! Start playing.");
    }
    @Override
    protected void startPlay() {
        System.out.println("Cricket Game Started. Enjoy the game!");
    }
    @Override
    protected void endPlay() {
        System.out.println("Cricket Game Finished!");
    }
}

class Football extends Game {
    @Override
    protected void initialize() {
        System.out.println("Football Game Initialized! Start playing.");
    }
    @Override
    protected void startPlay() {
        System.out.println("Football Game Started. Enjoy the game!");
    }
    @Override
    protected void endPlay() {
        System.out.println("Football Game Finished!");
    }
}
```


## Template vs Strategy

![[Bildschirm­foto 2023-01-24 um 20.55.42.png]]