It is a [[Behavioral patterns]].

The State pattern is a behavioral design pattern that allows an object to change its behavior when its internal state changes. The pattern is used to represent a finite state machine, in which an object can exist in one of several possible states, and its behavior changes based on which state it is currently in.

A common example of the State pattern is a vending machine. A vending machine can be in one of several states, such as "idle", "item selected", or "dispensing item". Each state corresponds to a different behavior - for example, when the vending machine is in the "idle" state, it will accept selections and money, but when it is in the "dispensing item" state, it will dispense the selected item and return any change.

### Advantages:
- Useful for objects which change their state at runtime.
- Uses polymorphism to define different behaviors for different states of an object.
- The selection of the subclass depends on the state of the object.
- Localizes state specific behavior.
- Extensibility and flexibility: easy to add more states for additional behavior.
- Avoids cluttered if-else or switch-case statements.
- Makes state transitions explicit
- <u>Comparison with bridge pattern</u>: the selection of the subclass is done at system initialization time.
- <u>Comparison with strategy pattern</u>: the selection of the subclass depends on an external policy.

## UML state chart diagram
![[Bildschirm­foto 2023-01-24 um 20.21.03.png]]
![[Bildschirm­foto 2023-01-24 um 20.22.05.png]]
![[Bildschirm­foto 2023-01-24 um 20.21.40.png]]

## State pattern example

![[Bildschirm­foto 2023-01-24 um 20.23.52.png]]