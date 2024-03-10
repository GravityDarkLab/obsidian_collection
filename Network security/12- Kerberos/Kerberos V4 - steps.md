[[12- Kerberos and other Frameworks for Client Authentication]].

1. **Authentication Request**:
   - **Client to Authentication Server (AS)**: The client sends an authentication request to the AS. This request includes the **client's ID**, the **TGS ID**, the **timestamp**, and the requested lifetime for the TGS ticket (**RequestedTicketLifetimeTGS**).

2. **AS Response**:
   - **AS to Client**: If the client is verified, the AS responds with two items: 
     1. A **client/TGS** session key encrypted with the client's secret key.
     2. A **Ticket Granting Ticket (TGT)**, which includes the client ID, client network address, ticket validity period, client/TGS session key, encrypted with the TGS's secret key.

3. **TGS Request**:
   - **Client to TGS**: The client sends a message to the TGS, including the TGT received from the AS (still encrypted), the ID of the requested service, the current timestamp, and a authenticator (which includes the client's ID and timestamp), ==encrypted with the client/TGS session key==.

4. **TGS Response**:
   - **TGS to Client**: If the request is valid, the TGS sends two items to the client:
     1. A **service session key** encrypted with the client/TGS session key.
     2. A **service ticket**, which includes the client's ID, network address, validity period, and the service session key, encrypted with the service's secret key.

5. **Service Request**:
   - **Client to Server**: The client sends the service ticket and an authenticator (which includes the client's ID and the timestamp), encrypted with the service session key, to the service server.

6. **Server Response**:
   - **Server to Client**: If the service ticket and the authenticator are valid, the server sends a confirmation to the client, typically including the timestamp found in the client's authenticator encrypted with the service session key, to prove that it decrypted the authenticator.


![[Screenshot 2024-02-04 at 16.26.16.png]]