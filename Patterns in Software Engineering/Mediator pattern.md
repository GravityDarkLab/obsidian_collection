It is a [[Behavioral patterns]].

`Good choice if you have to deal with a set of objects that are tightly coupled and hard to maintain`.
`Extracts the communication logic in a single object`.


The Mediator pattern is a behavioral design pattern that promotes the loose coupling of objects by providing a central point of communication between them. The Mediator pattern defines an object that acts as a mediator between a set of objects, encapsulating the communication logic and reducing the dependencies between the objects.

In the Mediator pattern, the objects that need to communicate with each other are called Colleagues, and the object that mediates the communication is called Mediator. The Mediator object provides a common interface for the Colleagues to communicate and it's responsible for coordinating the communication between them. The Colleagues do not need to know about each other, they only need to know about the Mediator and the Mediator is aware of all the Colleagues.
![[Bildschirm­foto 2023-01-25 um 17.10.39.png]]

## Checklist:
-   Are there many objects that need to communicate with each other and are causing tight coupling?
-   Are you finding it difficult to add or remove new objects to the system?
-   Do you need to change the communication logic between objects?
-   Do you need to encapsulate the communication logic in a central place?
-   Do you need to control the communication between objects?

If the answer to any of these questions is yes, then the Mediator pattern might be a good choice for your system. The Mediator pattern helps to promote loose coupling, reduce dependencies, and encapsulate communication logic in a central place. It also makes it easier to add or remove new objects to the system and change the communication logic.


## Code example:
```java
interface ChatMediator {
    void sendMessage(String message, User user);
    void addUser(User user);
}

class ChatRoom implements ChatMediator {
    private List<User> users;

    public ChatRoom() {
        this.users = new ArrayList<>();
    }

    @Override
    public void addUser(User user) {
        this.users.add(user);
    }

    @Override
    public void sendMessage(String message, User user) {
        for (User u : this.users) {
            // message should not be received by the user sending it
            if (u != user) {
                u.receive(message);
            }
        }
    }
}

abstract class User {
    protected ChatMediator mediator;
    protected String name;

    public User(ChatMediator med, String name) {
        this.mediator = med;
        this.name = name;
    }

    public abstract void send(String msg);

    public abstract void receive(String msg);
}

class UserImpl extends User {
    public UserImpl(ChatMediator med, String name) {
        super(med, name);
    }

    @Override
    public void send(String msg) {
        System.out.println(this.name + ": Sending Message=" + msg);
        mediator.sendMessage(msg, this);
    }

    @Override
    public void receive(String msg) {
        System.out.println(this.name + ": Received Message:" + msg);
    }
}
```

In this example, when a user wants to send a message, it calls the `send` method on the `ChatMediator` with the message and the `ChatMediator` is responsible for forwarding the message to all the other users except the sender. This way, the `User` objects are loosely coupled and the communication logic is encapsulated in the `ChatMediator` class.

## Advantages

> The Mediator pattern is useful when you have a system with a lot of objects that need to communicate with each other, it helps to promote loose coupling and reduce the dependencies between the objects. It also facilitates the addition or removal of new objects to the system, as the communication logic is centralized in the Mediator, and the Colleagues do not need to know about each other. This makes the system more flexible and easier to maintain.

> Another advantage of the Mediator pattern is that it makes it easier to change the communication logic, as it's encapsulated in the Mediator. For example, if you want to change the way messages are sent or received, you only need to change the Mediator class and the Colleagues will not be affected.