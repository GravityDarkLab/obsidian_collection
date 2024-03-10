Kerberos is a network authentication protocol designed to provide strong authentication for client/server applications by using **secret-key cryptography**. Its framework revolves around the concept of a **trusted third party** to ==facilitate secure connections== between a client and a server across an insecure network. Here’s a simplified breakdown:

1. **Key Components**:
   - **Key Distribution Center (KDC)**: Acts as the trusted third party. It contains two parts:
     - **Authentication Server (AS)**: Verifies the identity of users and services.
     - **Ticket Granting Server (TGS)**: Issues tickets for accessing services.
   - **Client**: The user or service requesting access.
   - **Server**: The service provider.

2. **How it Works**:
   - **Initial Authentication**:
     - The client requests an authentication token from the AS in the KDC.
     - The AS verifies the client's credentials (usually a username and password). If valid, it issues a Ticket Granting Ticket (TGT) encrypted with a secret key.
   - **Ticket Granting**:
     - The client presents the TGT to the TGS to request access to a specific service.
     - The TGS verifies the TGT, and if valid, issues a service ticket for the client.
   - **Service Request**:
     - The client uses the service ticket to authenticate itself to the server.
     - The server verifies the ticket and grants access to the service.

3. **Security Features**:
   - **Mutual Authentication**: Both the **==client and the server verify each other's identity==**.
   - **Temporal Limitations**: Tickets have a **==limited validity period==**, reducing the risk of misuse.
   - **Encryption**: All communications are encrypted, **==protecting against eavesdropping and replay attacks==**.

![[Screenshot 2024-02-04 at 16.18.13.png]]
> See details here: [[Kerberos V4 - steps]]
### Design Goals of kerberos
#### Security:
- Eavesdroppers or active attackers should not be able to obtain the necessary information to impersonate a user when accessing a service.
#### Reliability:
- Every use of the service requires prior authentication -> Should be highly reliable and available.
#### Transparency:
- The authentication process should be transparent and user should only witness the "enter the password"
#### Scaleability:
- Support large number of clients and servers

### Kerberos–Pre-Authentication
- [[12.1- Kerberos–Pre-Authentication]].

### Options for Authentication with external AS
![[Screenshot 2024-02-04 at 16.06.51.png]]

