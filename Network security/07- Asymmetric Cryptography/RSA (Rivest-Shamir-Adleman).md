[[7-Asymmetric Cryprography]].

- [[#How It Works|How It Works]]
- [[#Security|Security]]
- [[#Practical Use|Practical Use]]
- [[#RSA for Confidentiality|RSA for Confidentiality]]
- [[#What is OAEP?|What is OAEP?]]
- [[#How OAEP Works|How OAEP Works]]
- [[#Benefits of Using OAEP|Benefits of Using OAEP]]
- [[#Limitations|Limitations]]
- [[#Example:|Example:]]
	- [[#Example:#Step 1: Key Generation|Step 1: Key Generation]]
	- [[#Example:#Step 2: Encryption|Step 2: Encryption]]
	- [[#Example:#Step 3: Decryption|Step 3: Decryption]]
- [[#Conclusion|Conclusion]]


### How It Works
RSA involves a series of mathematical operations. Here's a simplified overview:

1. **Key Generation**:
   - **Choose two distinct large prime numbers** $p$ and $q$.
   - **Compute $n = pq$**: $n$ is used as the modulus for both the ==public== and ==private== keys. Its length, usually ==expressed in bits, is the key length==.
   - **Calculate $\phi (n) = (p-1)(q-1))$**: This is Euler's totient function.
   - **Choose an integer $e$**: This is the public exponent. It should be co-prime to $\phi (n)$ and typically is $65537$ for its balance of security and performance also $1<e<\phi(n)$
   - **Determine $d$**: Calculate the modular ==multiplicative inverse== of $e\mod\phi(n)$. $d$ is the private exponent. $e.d=1\mod\phi(n)$.

2. **Public and Private Keys**:
   - **Public Key**: Consists of the modulus $n$ and the public exponent $e$.
   - **Private Key**: Consists of the modulus $n$ and the private exponent $d$.

3. **Encryption**:
   - Given a plaintext message $M$, it is encrypted to ciphertext $C$ using the recipient's public key $(e, n)$ as $C = M^e \mod n$.

4. **Decryption**:
   - The ciphertext $C$ is decrypted back to the message $M$ using the recipient's private key $(d, n)$ as $M = C^d \mod n$.

### Security

The security of RSA arises from the fact that it is currently **==infeasible to factorize a large integer composed of two large prime numbers==** multiplied together, especially as the key length increases.

### Practical Use

- **Digital Signatures**: RSA can be used to sign a message, ensuring authenticity and integrity.
- **Encryption**: Used to encrypt data, commonly seen in secure web browsing (HTTPS).

### RSA for Confidentiality

In the context of confidentiality, RSA is used to encrypt data to ensure that only the intended recipient, who possesses the corresponding private key, can decrypt and access the information.
### What is OAEP?

**Optimal Asymmetric Encryption Padding (OAEP)** is a padding scheme used with RSA encryption to increase security. It addresses vulnerabilities inherent in straightforward implementations of RSA, such as its deterministic nature and susceptibility to certain attacks.
### How OAEP Works

- **Adding Randomness**: OAEP introduces randomness into the encryption process. This randomness means that even if the same plaintext is encrypted multiple times, it will result in different ciphertexts each time.
- **Process**:
    - **Message and Random Seed**: The plaintext message is combined with a random seed using a masking function.
    - **Padding**: The result is then padded to match the size of the RSA key being used.
    - **RSA Encryption**: The padded message is then encrypted using the standard RSA encryption process. 
- **Decryption**: The decryption process reverses these steps, using the RSA private key to first decrypt the message and then carefully remove the padding to retrieve the original plaintext.

### Benefits of Using OAEP
- **Security Against [[Chosen-Plaintext Attacks]]**: By adding randomness, OAEP mitigates the risk of chosen-plaintext attacks.
- **Prevents Message Guessing**: Since the same plaintext encrypts to different ciphertexts, attackers cannot use ciphertexts to guess the message.
### Limitations

- **Computational Intensity**: RSA is much slower compared to symmetric key algorithms.
- **Key Size**: Requires larger key sizes for equivalent security compared to symmetric key algorithms.

### Example:
#### Step 1: Key Generation
1. **Choose two prime numbers**: 
   - Let's say $p = 61$ and $q = 53$.
2. **Compute** $n = pq$: 
   - $n = 3233$.
3. **Calculate $phi (n)$**:
   - $phi(3233) = (61 - 1)(53 - 1) = 3120$.
4. **Choose public exponent $e$**:
   - A common choice is $e = 17$ (must be co-prime to $\phi(n)$).
5. **Determine private exponent $d$**:
   - $d$ is the modular multiplicative inverse of $e$ modulo $\phi (n)$. Let's say $d = 2753$.

Now, our public key is $K_{pub}=(n, e) = (3233,17)$ and our private key is $K_{sec}=(n, d) = (3233,2753)$.

#### Step 2: Encryption
$$Enc(m,K_{pub}):=Enc(m,n,e):= c ≡ m^e \mod n$$

Suppose Alice wants to send the message "HI" = 89 to Bob
- **Encrypt the message**:
  - Using Bob's public key, the ciphertext $C$ is calculated as $C = M^e \mod n$.
  $\rightarrow C = 89^{17} \mod 3233 = 2182$.

#### Step 3: Decryption
$$Dec(c,K_{sec}) = Dec(c,n,d) := m ≡ c^d \mod n$$
Now, Bob receives the ciphertext 2182. To decrypt this:

- **Decrypt the message**:
  - Using his private key, Bob computes $M = C^d \mod n$.
  $\rightarrow M = 2182^{2753} \mod 3233 = 89$.

### Conclusion

RSA is a cornerstone of modern cryptographic practice. Despite its computational intensity, it's critically important in the current landscape of digital security for both encryption and digital signatures. Its real strength lies in the mathematical complexity, making it a reliable choice for secure communication.

> **Security Consideration**: Encrypting a message of 0 is not inherently insecure, but it's important to remember that RSA should not be used to encrypt actual messages directly, especially very short or predictable ones.
> ==This is because RSA, without any padding or additional security measures, can be vulnerable to certain types of attacks (like [[Chosen-Plaintext Attacks]])==. Instead, RSA is often used to encrypt a key used for symmetric encryption or for digital signatures.

