
![[Pasted image 20240105093248.png]]
## What is it?

 - Asymmetric cryptography, also known as public key cryptography, uses two different but mathematically related keys: a public key and a private key.

```
Public key is for encryption or verification, and it's openly available.
Private key is for decryption or signing, and it's kept secret.
```
## How does it work?

- **Encryption**: If Alice wants to send a secure message to Bob, she encrypts it using Bob’s public key.
- **Decryption**: Upon receiving the message, Bob decrypts it using his private key.

### Key Characteristics#

- **Non-Interchangeability**: You cannot decrypt a message with the same key used for encryption.
- **Security**: The security hinges on the impossibility of deriving the private key from the public key.

### Common Algorithms

1. **[[RSA (Rivest-Shamir-Adleman)]]**: One of the first and most widely used algorithms.
2. **[[ECC (Elliptic Curve Cryptography) - Outlook]]**: Uses elliptic curves for a more efficient, equally secure process.
3. **[[Diffie-Hellman key exchange protocol]]**: Used for secure key exchange.
4. [[Threshold Signature Schemes]].

### Limitations

- Very expensive.
- Slower than symmetric crypto or hashing
- Unsuitable to encrypt larger amount of data

### Why not?

- [[7.1- Hybrid Encryption Scheme]].
- Use public key cryptography to securely exchange (ephemeral) symmetric key.
- Use symmetric cryptography to encrypt the actual payload data.

### But how are the keys exchanged?
- For that there is the  [[9- Public Key Infrastructures]]
- You can do that manually which requires high effort, or using the [[9- Public Key Infrastructures]].
- Many moderns Apps exchange Keys for you. 
	- You can validate the authenticity of the keys you are using with special functions.