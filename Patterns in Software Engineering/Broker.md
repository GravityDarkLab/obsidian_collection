It is an [[Architectural patterns]].


The broker pattern allows for the separation of concerns between different components of a system by acting as an intermediary between them. It allows components to communicate with each other without needing to know about each other's implementation details.

A common use case for the broker pattern is in systems that need to handle events or messages. The broker acts as a central hub for handling these events or messages, and it routes them to the appropriate components for processing.

## Code example:
```java
interface Event { /* event interface */ }
class EventA implements Event { /* event data */ }
class EventB implements Event { /* event data */ }

interface EventHandler { 
  void handleEvent(Event event);
}
class EventHandlerA implements EventHandler { 
  public void handleEvent(Event event) { /* handle EventA */ }
}
class EventHandlerB implements EventHandler { 
  public void handleEvent(Event event) { /* handle EventB */ }
}

class EventBroker {
    private Map<Class<? extends Event>, List<EventHandler>> handlers;

    public EventBroker() {
        handlers = new HashMap<>();
    }
    public void addEventHandler(Class<? extends Event> type, EventHandler handler) {
        handlers.computeIfAbsent(type, k -> new ArrayList<>()).add(handler);
    }
    public void removeEventHandler(Class<? extends Event> type, EventHandler handler) {
        List<EventHandler> handlers = this.handlers.get(type);
        if (handlers != null) {
            handlers.remove(handler);
        }
    }
    public void sendEvent(Event event) {
        List<EventHandler> handlers = this.handlers.get(event.getClass());
        if (handlers != null) {
            for (EventHandler handler : handlers) {
                handler.handleEvent(event);
            }
        }
    }
}
```
In this example, the `EventBroker` class acts as a central hub for handling events. Components that need to receive events register themselves with the broker, and the broker routes the events to the appropriate components for processing. The `Event` interface and its implementation `EventA`, `EventB` are the events that the system will handle. The `EventHandler` interface and its implementation `EventHandlerA`, `EventHandlerB` are the event handlers that will handle the events.
```java
EventBroker broker = new EventBroker();
EventHandlerA handlerA = new EventHandlerA();
EventHandlerB handlerB = new EventHandlerB();

broker.addEventHandler(EventA.class, handlerA);
broker.addEventHandler(EventB.class, handlerB);

EventA eventA = new EventA();
EventB eventB = new EventB();

broker.sendEvent(eventA); // EventHandlerA will handle the event
broker.sendEvent(eventB); // EventHandlerB will handle the event
```
In this way, the broker pattern allows for loose coupling between the components of the system, and it makes it easy to add or remove components without affecting the rest of the system.

## Design goals addressed by the broker:
- **Low coupling**:
	- Decoupling the service implementation and presentation mechanisms.
	- Decoupling also the service implementation and the communication mechanisms.
- **Location transparency**:
	- A client can use a service independently of the location of the server that offers it.
- **Runtime extensibility**:
	- Being able to add, remove and exchange components at runtime.

## Steps to realize a broker pattern:
1. Provide the object model and service definitions:
	1. Define client and server objects: **==the state of the server objects should be private==**.
	2. Clients may change or read the <u>server’s state</u> **==only by passing requests to the broker==**.
	3. Define the service interfaces.
 2. Define the broker service:
	 1. Specify the services offered by the Broker (register, call, ...).
3. Implement the broker component and proxy objects at client and server side:
	1. Serialize and deserialize objects.
	2. Pass service calls to the broker.
	3. Implement the interface access routines for the proxies.
	4. Implement the client and the server.

## Synchronous vs asynchronous communication:
- **Synchronous**:
	- The client issues the method call and waits until the result is returned.
- **Asynchronous**:
	- The client issues the method call, and continues --> non-blocking method call.
	- Gets notified by the broker when the result is ready.
	- This is usually implemented using callbacks.
See [[Broker vs Client dispatcher server]].
