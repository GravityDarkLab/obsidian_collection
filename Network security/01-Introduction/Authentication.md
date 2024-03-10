
### Example:

![[Pasted image 20240111084029.png]] 
### Authentication is a Proof!

- Alice generates a fresh random value and sends it encrypted with Bob’s public key to Bob.
	$\rightarrow$ **Challenge**
- Bob decrypts challenge with his private key and sends the random number back to Alice.
	$\rightarrow$ **Response** 
- If response is as expected (correct), Bob participated in the protocol.

- **Reasoning**:
	- Alice knows Bob’s public key; Alice assumes that only Bob has access to his private key.
	- Alice generates random number, encrypts it with Bob’s public key.
	- Alice observes that someone was able to decrypt her challenge and respond to it.
	- Alice reasons: As only Bob has access to his private key, this someone must be Bob!

### Trusted Third Party (TTP)
> TTPs help to make key exchange more scalable.

Example of TPPs:
- [[9- Public Key Infrastructures]] / CA passively helps with key establishment.
	- Certificates issued by CA are utilized by entities during key establishment
	- Trust anchor: (Root) CA Certificates in root store
- **Authentication Server (AS)** actively helps with key establishment.
	- Trust anchor: Long-term shared key between AS and each entity.
	- An AS reduces the number of long-term shared keys in the system $(O (n^2) → O (n))$.

