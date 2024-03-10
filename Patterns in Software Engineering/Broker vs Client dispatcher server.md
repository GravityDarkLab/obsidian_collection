[[Broker]] vs [[Client dispatcher server]] vs [[Client-Server architecture]].
![[Bildschirm­foto 2023-01-28 um 13.32.35.png]]![[Bildschirm­foto 2023-01-28 um 13.32.45.png]]![[Bildschirm­foto 2023-01-28 um 13.32.59.png]]![[Bildschirm­foto 2023-01-28 um 13.35.06.png]]

-   The client-dispatcher-server pattern typically involves a client component making requests to a central dispatcher, which then routes the requests to the appropriate server component for processing. In contrast, the broker pattern typically involves components sending events or messages to a central hub (the broker), which then routes the events or messages to the appropriate components for processing.
    
-   In the client-dispatcher-server pattern, the client is typically aware of the specific server it is communicating with. In contrast, in the broker pattern, the components typically do not need to know about the specific other components they are communicating with.
    
-   The client-dispatcher-server pattern is often used in systems where the client needs to make requests and receive a response, while the broker pattern is often used in systems where the components need to communicate with each other asynchronously.
    
-   In the client-dispatcher-server pattern, the client is typically responsible for creating and sending the request, while in the broker pattern, the components typically do not need to know about the specifics of the messages they are sending or receiving.
    

> Overall, both patterns are useful for decoupling different components of a system and providing a flexible and extensible architecture, but they are often used in different types of systems and for different types of communication.