It is part of the [[Testing patterns]].


## Testing the Client:
- In order to write integration client tests, you need to mock the remote service using:
	- OkHttp WebMockServer.
	- WireMock.
	- Testcontainer Mockserver.
	- Spring MockRestServiceServer.
> When testing the client component of a Client-Server application, it's often necessary to mock the remote service in order to isolate the client from the server and test it in isolation. Mocking the remote service allows you to simulate the server's behavior and response without actually having to connect to a live server. This makes it easier to write tests that are fast, repeatable, and reliable.

![[Bildschirm­foto 2023-01-31 um 18.59.12.png]]
![[Bildschirm­foto 2023-01-31 um 19.00.14.png]]


## Testing the server:
- In order to write integration server test, your need to mock the client.
- In particular invoking REST calls and verifying the correct responses is necessary.

![[Bildschirm­foto 2023-01-31 um 19.01.49.png]]

![[Bildschirm­foto 2023-01-31 um 19.02.06.png]]

## Code example

![[Bildschirm­foto 2023-01-31 um 19.04.20.png]]