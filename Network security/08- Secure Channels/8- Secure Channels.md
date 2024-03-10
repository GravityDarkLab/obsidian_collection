- [[#Introduction|Introduction]]
- [[#Key Concepts|Key Concepts]]
- [[#Types of Secure Channels|Types of Secure Channels]]
- [[#MAC-then-Enc vs. MAC & Enc vs. Enc-then-MAC|MAC-then-Enc vs. MAC & Enc vs. Enc-then-MAC]]
- [[#Secure Channel Implementation|Secure Channel Implementation]]
- [[#Secure Channel (ESP) in the OpenBSD Kernel|Secure Channel (ESP) in the OpenBSD Kernel]]
- [[#Authenticated Encryption With Associated Data (AEAD)|Authenticated Encryption With Associated Data (AEAD)]]
- [[#Attacks against a Secure Channel|Attacks against a Secure Channel]]

See  [[meme.png]]

`They are transport abstraction`.
`They securely transport communication`.
`Security Goal: Confidentiality, Integrity, Authenticity`
## Introduction

A secure channel is a communication link that provides **confidentiality**, **integrity**, and **authentication**, ensuring that data is ==safely and accurately transmitted between communicating parties==. These channels are crucial in protecting sensitive information from unauthorized access and tampering during transmission over networks.

## Key Concepts

1. **Encryption**: Encryption can be [[4- Symmetric Encryption]] (same key for encryption and decryption) or [[7-Asymmetric Cryprography]] (different keys for encryption and decryption).
2. **Authentication**: Ensuring that the parties at either end of the communication are who they claim to be. This is often done using digital certificates and cryptographic keys.
3. **Integrity Checks**: Making sure that the data has not been altered during transmission. This is typically achieved through cryptographic hashing and digital signatures. 
   $\rightarrow$ [[5- Cryptographic Hash Functions and Message Authentication Codes]].
	1. It insures that message are received in correct order.
	2. No duplicates/replayed messages.

> `Secure channels require a long term (symmetric/ asymmetric) key to work`.
> `Excahnging/agreeing on long term keys is often done out of band`.
> 

> `Typically, keys are derived from the session key for authentification and encryption`.
## Types of Secure Channels

1. **SSL/TLS (Secure Sockets Layer/Transport Layer Security)**: These protocols provide secure communication over the internet. When you visit a website with HTTPS, it uses SSL/TLS to encrypt the data between your browser and the web server.

2. **VPN (Virtual Private Network)**: A VPN extends a private network across a public network, enabling users to send and receive data across shared or public networks as if their computing devices were directly connected to the private network.

3. **SSH (Secure Shell)**: Used primarily for accessing shell accounts on UNIX systems, SSH is a protocol for secure remote login and other secure network services over an insecure network.

**Examples and Explanations**

1. **SSL/TLS in Online Banking**: When you access your bank's website, SSL/TLS ensures that your sensitive financial information is encrypted. This prevents eavesdroppers on the network from intercepting your data.

2. **VPN for Remote Work**: Employees working remotely can use a VPN to securely connect to their company's internal network. This allows them to access resources as if they were physically at the office, with the data being encrypted during transit.

3. **SSH for Server Management**: Administrators use SSH to securely log in to remote servers. For example, a system admin can securely access a server located in a data center from their laptop to perform maintenance tasks.

## MAC-then-Enc vs. MAC & Enc vs. Enc-then-MAC
- `MAC: Message Authentication Code`.
- $k-int$: Key for integrity 
- $k-enc$: Key for encryption
- [[8.1- MAC-then-Enc]]:  $Enc_{k-enc}(m,MAC_{k-int}(m))$
- [[8.2- MAC & Enc]]: $Enc_{k-enc}(m),MAC_{k-int}(m)$
- [[8.3- ENC-then-MAC]]: $Enc_{k-enc}(m),MAC_{k-int}(Enc_{k-enc}(m))$.

**Comparison and Best Practices**
- When comparing these methods, [[8.3- ENC-then-MAC]] generally offers the best security by ensuring both the **confidentiality** and **integrity** of messages.
- [[8.1- MAC-then-Enc]], while simpler, poses security risks, particularly in the context of **padding oracle attacks**.
- [[8.2- MAC & Enc]] offers a balance but requires careful implementation, particularly in ensuring that the MAC does not reveal information about the plaintext.

## Secure Channel Implementation
- See [[8.4- Secure Channel Implementation]].

## Secure Channel (ESP) in the OpenBSD Kernel
- See [[8.5- Secure Channel (ESP) in the OpenBSD Kernel]].


## Authenticated Encryption With Associated Data (AEAD)
- In order to establish a secure channel, quite a lot has to be considered:
	- Encryption (selection of the right cipher and mode of operation, IV, sequence numbers, key, . . . )
	- Integrity protection/authentication (selection of the right MAC construction, key, feed the right parameters (IV, sequence numbers, ciphertext, ...) into the function, . . .
	- Using the crypto primitives in the right order (Enc-then-Mac)
- All in one solution:
	- [[8.6- Authenticated Encryption With Associated Data (AEAD)]].

## Attacks against a Secure Channel 
- [[8.7- Attacks using Stream Cipher]].
- [[8.8- Attacks using Padding oracle]].