- [[#Definition|Definition]]
- [[#Common symmetric encryption algorithms|Common symmetric encryption algorithms]]
- [[#Modes of Encryption|Modes of Encryption]]
- [[#What security goals did we fulfil?|What security goals did we fulfil?]]

### Definition

> Symmetric encryption is a type of encryption where the same key $k$ is used for both encrypting and decrypting data.
-  $m: \text{Plaintext}$
- $c: \text{encrypted plaintext}$
- $c=Enc_k(m): \text{Encryption}$
- $m=Dec_k(c): \text{Decryption}$
- $Dec_k(Enc_k(m)) = m$
`A cipher is secure if the best known attack is brute-forcing all keys`.
### Common symmetric encryption algorithms

`The cipher method must not be required to be secret, and it must be able to fall into the hands of the enemy without inconvenience.` – Auguste Kerckhoffs

- **Block cipher**: (`Block lenght and key size do not need to be the same`).
	- **AES (Advanced Encryption Standard)**.
	- **DES (Data Encryption Standard)**.
	- **3 DES (Triple DES)**. 
- **Stream cipher**: (`same size`)
	- **One-Time-Pad (OTP)**: it is a stream cipher that XORs the Plaintext $m$ with a key $k=otp$ called one-time-pad. The key must be same size as $m$ and be perfectly random. It can be used only once.

> **AES is widely used today due to its strength and efficiency**.

### Modes of Encryption

1. **[[Electronic Codebook (ECB)]]**: The simplest form, where each block of data is encrypted separately. It's fast but not very secure, as ==identical plaintext blocks result in identical ciphertext blocks==. 

2. **[[Cipher Block Chaining (CBC)]]**: Each block of plaintext is **XORed** with the previous ciphertext block before encryption. This mode **uses an initialization vector (IV)** for the first block. ==It's more secure than ECB but can propagate errors; if one block is corrupted, it affects the decryption of all subsequent blocks==.

3. **[[Output Feedback (OFB)]])**: This mode turns a block cipher into a stream cipher. It generates keystream blocks, which are then XORed with the plaintext blocks. Error propagation is not an issue here; a single bit error in ciphertext affects only the corresponding bit in the decrypted plaintext.

4. **[[Counter (CTR)]]**: It encrypts a counter value for each block of plaintext. The counter is typically a sequence of numbers ([[nonce]]). Like OFB, CTR mode creates a stream cipher and does not have error propagation issues.

### What security goals did we fulfil?
- **Confidentiality**?  $\Rightarrow$ Yes.
- **Integrity**? $\Rightarrow$ No
	- Example: An attacker could modify c.
	- $Dec_k(c)$ will most probably yield garbled text.
	- ==Receiver can only assume that the message was modified but not prove it!==
- **Authenticity**? $\Rightarrow$ No!
	- Attacker could just send some random c and spoof Alice’s IP address.
	- $Dec_k(c)$ will yield garbled text. 
	- ==Receiver can only assume that the message is not authentic but not prove it!==

- [[4.1- Attacking Symmetric Ciphers]].