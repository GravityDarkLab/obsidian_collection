It is an [[Architectural patterns]].

The client-server architectural style is a design pattern that separates the functionality of an application into two parts: the client and the server. The client is responsible for the user interface and the presentation logic, while the server is responsible for the data storage and the business logic.
![[Bildschirm­foto 2023-01-24 um 18.15.56.png]]
- Client server systems use a request-response protocol.
- Peer to peer communication is often needed.

A good example of a client-server architecture is the World Wide Web. The web browser (the client) sends HTTP requests to web servers to retrieve web pages and other resources. The web server (the server) responds with the requested resources, which are then displayed in the browser.

Another example is an online shopping application, where the client is a web or mobile application that allows users to browse and purchase items, while the server is a set of [[RESTful]]services that handle the business logic and access the database to retrieve and store data.

## Code example:
```java
import java.io.*;
import java.net.*;

public class Server {
    public static void main(String[] args) {
        try {
            ServerSocket serverSocket = new ServerSocket(5555);
            while (true) {
                Socket socket = serverSocket.accept();
                BufferedReader in = new BufferedReader(new InputStreamReader(socket.getInputStream()));
                PrintWriter out = new PrintWriter(socket.getOutputStream(),true);
                String request = in.readLine();
                String response = handleRequest(request);
                System.out.println(response);
                System.out.flush();
                socket.close();
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }

    private static String handleRequest(String request) {
        if (request.equalsIgnoreCase("Hello")) {
            return "World!";
        } else {
            return "Unknown request";
        }
    }
}
```

```java
import java.io.*;
import java.net.*;
import java.util.Scanner;

public class Client {
    public static void main(String[] args) {
        try {
            Scanner scanner = new Scanner(System.in);
            Socket socket = new Socket("localhost", 5555);
            BufferedReader in = new BufferedReader(new InputStreamReader(socket.getInputStream()));
            PrintWriter out = new PrintWriter(socket.getOutputStream(), true);

            System.out.print("Enter your request: ");
            String request = scanner.nextLine();

            out.println(request);
            String response = in.readLine();

            System.out.println("Server response: " + response);

            socket.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

This example implements a simple server that listens on port 5555 and waits for clients to connect. Once a client connects, the server reads a request from the client, processes it using the `handleRequest` method, and sends a response back to the client.

On the client side, the user is prompted to enter a request, which is then sent to the server. The client then reads the response from the server and displays it to the user.



![[Bildschirm­foto 2023-01-27 um 21.45.23.png]]![[Bildschirm­foto 2023-01-27 um 21.47.02.png]]