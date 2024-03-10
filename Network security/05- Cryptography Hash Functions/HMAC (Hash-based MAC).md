 
- **What It Is**: HMAC combines a cryptographic hash function with a secret key. It's widely used because of its simplicity and effectiveness.
- **How It Works**:
    1. The secret key is combined with the input message.
    2. This combination is then passed through a hash function.
	    - To strengthen security, HMAC actually applies the hash function twice in an "inner" and "outer" layer, with the key and the message processed in a particular way involving exclusive-or (XOR) operations with two different constant values
    3. The output hash (the HMAC) is then used for authentication.
- **Properties**:
    - **Security**: Relies on the security of the underlying hash function (like SHA-256).
    - **Keyed**: The secret key adds an additional layer of security.
- **Use Case**: Common in web security for data integrity and authentication, like in API authentication.

- The construction $H(K|m|K)$ - prefix-suffix mode. - Was used.
- The most used is: $H(K\oplus opad|H(k\oplus ipad|m))$
	- The length of the key $K$ is first extended to the block length required for the input of the hash function H by appending zero bytes.
	- Then it is **XOR’ed** respectively with **two constants ==opad== and ==ipad==**.
	- The hash function is applied twice in a nested way.
	  $\rightarrow$ Currently no attacks have been discovered on this MAC function.