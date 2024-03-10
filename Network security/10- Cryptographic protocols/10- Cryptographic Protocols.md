
- We use the [[Dolev-Yao attacker model]].
- After running our cryptographic protocol, the following goals are met:
	- Alice and Bob have a shared a session key for a secure channel.
	- Alice and Bob have agreed on the cryptographic algorithms to be used for the secure channel
	- Mutual authentication and freshness: Alice (Bob) must be able to verify that Bob (Alice) participated in ==**the protocol run and that he (she) is “alive”**==.
	- Alice and Bob must know that $K_{A,B}$ is newly generated.

## Entity Authentication and Key Establishment

#### Entity Authentication
- An authentication protocol is run **and at the end participants are ensured of the identity of other participants**.
- **Types**:
	- Authenticity of one entity.
	- Authenticity of both entities is shown: mutual authentication.
See: [[Authentication]]
#### Key Establishment
- A key is established between some protocol participants
- Key Transport: Some entity creates the key and sends it to other entities.
- Key Agreement: Multiple entities contribute to the generation of the key.

>  In practice, Entity Authentication and Key Establishment are often closely intertwined, in fact entity Authentication is often realised as authenticating key exchange (and other) parameters for Example:
>  - Instead of sending $(A , Password_{A ,B} , g^a \mod p , g, p)$, we send $(A, g^a \mod p, g, p, hmac_{Password_{A, B}}(A, g^a \mod p, g, p))$. 
>  - **==This allows B to authenticate the message and Alice!==**

See [[Key Establishment]].

#### Key Establishment without Entity Authentication

In general, **key establishment without entity and message authentication is not a good idea**.

> The reasons why protocols "Try 1" (Textbook DH) and "Try 2" (DH + password) failed were, that after a protocol run, neither Alice nor Bob know with whom they actually have exchanged a key and the exchanged key was not authenticated!


#### Entity Authentication without Key Establishment

- Example use case: Authorization
- Authentication is the basis for authorization. In some cases no session key is needed.

## Attack against Cryptographic Protocols
- **[[10.1- Relay Attack]]**.
- **[[10.2- NT LAN Manager (NTLM) Relay Attack]]**.
- **[[10.3- Forward Secrecy (Repetition)]]**.
- **[[10.4- Selection of used Algorithms- crypto agility]]**.

## Final Protocol
![[Pasted image 20240112083751.png]]
1. Messages 1 and 2 form a request-response pair where only information is exchanged.
2. Messages 3 and 4 form the authentication request-response pair with identity information and authentication.
3. Alice or Bob need to stop the communication when authentication fails or a wrong entity authenticates.
4. Message 3: Alice authenticates on her first message and on the nonce $N_B$ provided by Bob.
5. Message 4: Bob authenticates on his first message and on the nonce $N_A$ provided by Alice.


## Needham Schroeder Protocol
- **[[10.5- Needham Schroeder Protocol]]**.