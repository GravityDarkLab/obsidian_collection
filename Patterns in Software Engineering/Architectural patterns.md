- An architectural pattern is a general, high-level pattern for the organization of software. It provides a set of guidelines for designing the architecture of a software system. Architectural patterns are often used to describe the overall structure of a system, such as the layers, components, and interfaces that make up the system.

A software architecture consists of components and connectors:
- **Components** (subsystems) • Computational units with specified interfaces 
	- Examples: filters, databases, layers, objects...
- **Connectors** (communication): Interactions between the components (subsystems).
	- Examples: method calls, pipes, event broadcasts, shared data..


- There is mainly 4 types:
	- **From mud to struct**:
		- **[[Layered architectural style]]**: a pattern that organizes the components of a system into layers, where each layer provides a specific set of services to the layer above it.
		- **Pipe-and-Filter**: a pattern that decomposes a system into a series of processing stages, where each stage consumes the output of the previous stage and produces the input for the next stage.
		- **[[Blackboard]]**: subsystems are knowledge experts working together to solve a problem without a known solution strategy.
	- **Distributed systems**:
		- **[[Client-Server architecture]]**: a pattern that separates the presentation logic and the data storage logic into two separate components, the client and the server.
		- **[[Client dispatcher server]]**.
		- **Repository**: exchange of persistent data between multiple clients.
		- [[RESTful]]: representational state transfer, often used for web services, based on client server, layers and proxy.
		- **Microservices**: a pattern that decomposes a monolithic application into a collection of small, independently deployable services.
		- **[[Broker]]**: systems interact via remote service invocations
		- **Edge computing**: : synchronization of data, real-time access, and availability are realized simultaneously.
	- **Interactive systems**:
		- **[[Model-View-Controller (MVC)]]**: a pattern that separates the concerns of data management, user interface, and control flow.
		- **Model-View-ViewModel (MVVM)**: a pattern that separates the concerns of data management, user interface, and control flow in a way that's optimized for use with data binding frameworks.
	- **Adaptabel systems**:
		- **Microkernel**: extensible minimal functional core.
		- **Reflection**: self awareness provides information about system properties.

![[Bildschirm­foto 2023-01-24 um 11.11.02.png]]


> **Some challanges in distributed systems:
> 	- Systems are distributed and have to find and communicate with each other 
> 	→ Client server, client dispatcher server.
> 	- The distributed systems use different languages, platforms and protocols
> 	→ Broker.
> 	- Access control, authentication and encryption
> 	→ Proxy pattern.


> **Problem**:
> Distributed components need to communicate with each other:
> - Solution A: [[Client-Server architecture]].
> 	- Components implement the communication mechanism themselves.
> 	- <u>Disadvantage</u>: clients need to know the location of the server.
> - Solution B: [[Client dispatcher server]].
> 	- Place the communication mechanism in a name server, which decouples clients and servers and sets up the communication between both.
> 	- <u>Advantage</u>: addresses the nonfunctional requirement location transparency.
> - Solution C: [[Broker]].
> 	- Coordinate the communication between nodes.
> 	- Forwarding of requests, transmission of results, handling of exceptions.
> 	- Addresses the nonfunctional requirements location transparency and interoperability