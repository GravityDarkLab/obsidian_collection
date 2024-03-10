They are [[Architectural patterns]].


## Communication styles in distributed systems:
- From a programmer’s perspective you can broadly differentiate between message based and method based communication styles and mechanisms:
1. Message based:
	- The developer structures APIs as a set of messages that can be exchanged and encapsulate all necessary functionality.
	- Example: HTTP, REST, WebSockets, GraphQL 
2. Method based:
	- The developer structures APIs as a set of methods that have parameters and return types encapsulating remote functionality.
	- Example: RPC, RMI, CORBA, gRPC
	- `Method based communication is eventually implemented using message based communication.`

## REST as architectural style
- **Context**:
	- Shared resources and services with large numbers of distributed clients.
	- Access control and quality of service are important.
- **Problem**:
	- Manage a set of shared web resources and services.
	- Make them modifiable and reusable.
	- Support scalability and availability while spreading the resources across multiple distributed components.
- **Solution**: 
	- Provide an abstraction that models the structure and behavior of the world wide web.
	- Epresentational State Transfer (REST).
	- **REST was originally called the "HTTP object model"**


- REST (Representational State Transfer) is an architectural style for building web services. It is based on the principles of the HTTP protocol and the principles of the client-server architectural style.
- **==RESTful web services are designed to be lightweight, stateless, and to use HTTP methods such as GET, POST, PUT, and DELETE to manipulate resources on the server==**. -->**CRUD**.
- A RESTful web service exposes a set of resources, which are **identified by URIs (Uniform Resource Identifiers)**. Each resource can be manipulated using the standard HTTP methods. For example, to retrieve a resource, the client sends a GET request to the URI of the resource, and to update a resource, the client sends a PUT request to the URI of the resource.![[Bildschirm­foto 2023-01-28 um 17.35.03.png]]

- **Connector**:
	- Request / response: A request made to a web resource elicits a response with a body encoded in e.g. **XML** or **JSON**.
	- The protocol is stateless: no additional state information between two requests.
- **Constraints**:
	- Clients can connect to RESTful web services only via the request/response connector.

> 	REST is based on the client server, and layers as well as the proxy design pattern → often used in Microservices and Edge computing.


## Request response:
![[Bildschirm­foto 2023-01-28 um 17.30.11.png]]

## Idempotence and Safety

![[Bildschirm­foto 2023-01-28 um 17.34.08.png]]

## Status codes:

![[Bildschirm­foto 2023-01-28 um 17.41.23.png]]


## Example:
```java
@RestController
@RequestMapping("/api")
public class MyRestController {

  @Autowired
  private MyService myService;

  @GetMapping("/hello")
  public String hello() {
    return "Hello World!";
  }

  @GetMapping("/users")
  public List<User> getUsers() {
    return myService.getUsers();
  }

  @GetMapping("/users/{id}")
  public User getUserById(@PathVariable Long id) {
    return myService.getUserById(id);
  }

  @PostMapping("/users")
  public User addUser(@RequestBody User user) {
    return myService.addUser(user);
  }

  @PutMapping("/users/{id}")
  public User updateUser(@PathVariable Long id, @RequestBody User user) {
    return myService.updateUser(id, user);
  }

  @DeleteMapping("/users/{id}")
  public void deleteUser(@PathVariable Long id) {
    myService.deleteUser(id);
  }
}
```
