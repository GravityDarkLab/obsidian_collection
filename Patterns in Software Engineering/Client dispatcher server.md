It is an [[Architectural patterns]].

The client-dispatcher-server pattern is a pattern for designing networked systems where a client sends a request to a dispatcher, which then forwards the request to a server. The server processes the request and sends a response back to the dispatcher, which then forwards the response back to the client.

A good example of this pattern in Java would be a chat application where multiple clients connect to a server. The server acts as the dispatcher, receiving requests from clients and forwarding them to the appropriate chat room. The chat room then processes the request and sends a response back to the server, which then sends the response back to the appropriate client.

## Code example:
```java
class ChatClient {
    Socket socket;
    String message;
    ...
    void sendMessage(String message) {
        socket.getOutputStream().write(message.getBytes());
    }
    ...
}

class ChatServer {
    Map<Integer, ChatRoom> chatRooms;
    ...
    void handleRequest(Socket socket) {
        InputStream in = socket.getInputStream();
        byte[] message = new byte[1024];
        int len = in.read(message);
        String received = new String(message, 0, len);
        ...
        ChatRoom chatRoom = chatRooms.get(roomId);
        chatRoom.broadcast(received);
    }
    ...
}
```
In this example, the ChatClient **sends a message to the ChatServer by calling the sendMessage()** method. **The ChatServer then receives the message in its handleRequest() method and forwards it to the appropriate ChatRoom by calling the broadcast() method**.
```java
class ChatRoom {
    List<ChatClient> clients;
    ...
    void broadcast(String message) {
        for (ChatClient client : clients) {
            client.sendMessage(message);
        }
    }
    ...
}
```
The ChatRoom than processes the message by broadcasting it to all clients connected to the room. Each client receives the message and can display it in the chat interface.


![[Bildschirm­foto 2023-01-27 um 21.48.00.png]]![[Bildschirm­foto 2023-01-27 um 21.48.49.png]]![[Bildschirm­foto 2023-01-27 um 21.49.31.png]]

## Protocols in the client dispatcher pattern:
![[Bildschirm­foto 2023-01-27 um 21.51.00.png]]

## Steps to implement the client dispatcher server pattern:
1. During system design (in particular during the hardware-software mapping), identify the subsystems that act as clients and as servers and as dispatcher.
2. Decide on the communication mechanism to be used for the protocols:
	1. Communication between client and server, between client and dispatcher, between dispatcher and server.
	2. Using a single communication mechanism decreases the complexity of the implementation but may not be efficient
3. Specify the protocols between the components (set up the channel and define the transmission of data).
4. Decide on a naming scheme for the dispatcher • Introduce a naming scheme that uniquely identifies servers and is location transparent (URLs are ok, IP addresses are ok if the IP location is static).
5. Implement the dispatcher:
	- Decide on how to implement the 3 protocols using message based communication (sockets) or procedure calls (RPC, RMI).
	- Example: use local procedure calls if client and dispatcher reside in the same address space.
	- Design and implement the following classes: **==Request==**, **==Response==** and **==ErrorMessage==**
	- Design and implement a class **==repository==** that **maps server names to physical locations (use the repository pattern, implemented with hash table)**.
6. Implement the client and the server:
	- Decide whether server registers with the dispatcher at system startup time.
	- Decide if server can register und unregister during runtime

See [[Broker vs Client dispatcher server]].