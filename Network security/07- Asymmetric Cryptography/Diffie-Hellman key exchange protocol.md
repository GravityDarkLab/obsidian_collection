[[7-Asymmetric Cryprography]].

- [[#Introduction to Diffie-Hellman Key Exchange|Introduction to Diffie-Hellman Key Exchange]]
- [[#How It Works|How It Works]]
- [[#The Protocol Steps|The Protocol Steps]]
- [[#Why Is It Secure?|Why Is It Secure?]]
- [[#Example|Example]]
- [[#Practical Considerations|Practical Considerations]]
- [[#Conclusion|Conclusion]]

### Introduction to Diffie-Hellman Key Exchange

It is a method for securely exchanging cryptographic keys over a public channel.
It's one of the first protocols to enable **secure key exchange without needing a secure channel** for the initial exchange.
### How It Works

The protocol allows two parties to establish a shared secret key, used for subsequent encryption, without having to exchange any secret information. It's based on mathematical concepts from number theory and **==relies on the difficulty of the discrete logarithm problem==**.

### The Protocol Steps

1. **Agreement on Base Parameters**:
   - Both parties agree on a large prime number, $p$, and a base $g$, which is a primitive root modulo $p$.
   - `These numbers are not secret and can be known to potential eavesdroppers`.

2. **Private and Public Key Generation**:
   - Each party selects a private key. Let's say Alice chooses $a$ and Bob chooses $b$. These are kept secret.
   - They then generate their public keys: Alice computes $A = g^a \mod p$ and Bob computes $B = g^b \mod p$. These values are exchanged over the public channel.

3. **Shared Secret Computation**:
   - After exchanging public keys, Alice computes the shared secret using Bob’s public key: $s = B^a \mod p$.
   - Similarly, Bob computes the shared secret using Alice’s public key: $s = A^b \mod p$.
   - The beauty of this protocol is that both calculations result in the same value, $s$, which can now be used as a secret key for symmetric encryption.

### Why Is It Secure?

The security of the Diffie-Hellman Key Exchange lies in the difficulty of solving the discrete logarithm problem. Given $p$, $g$, and $g^x \mod p$, it is computationally infeasible to determine $x$. This means an eavesdropper, even knowing $p$, $g$, $A$, and $B$, cannot easily calculate the shared secret $s$.

### Example

Let's go through a simplified example:

- Suppose ( $p = 23$) and ($g = 5$).
- Alice chooses a private key ( $a = 6$) and Bob chooses ($b = 15$).
- Alice calculates her **public** key: ($A = 5^6 \mod 23 = 8$).
- Bob calculates his **public** key: ($B = 5^{15} \mod 23 = 19$).
- **Alice and Bob exchange their public keys**.
- Alice computes the shared secret: ($s = 19^6 \mod 23 = 2$).
- Bob computes the shared secret: ($s = 8^{15} \mod 23 = 2$).
- Both Alice and Bob now share the secret key ($s = 2$).

### Practical Considerations

- **Man-in-the-Middle Attacks**: While Diffie-Hellman is great for establishing a shared secret, it doesn't authenticate the parties. It’s vulnerable to man-in-the-middle attacks unless combined with authentication mechanisms.
- **Choosing Parameters**: The security also depends on choosing **large and secure** values for $p$ and $g$.
![[Pasted image 20240105121715.png]]
### Conclusion

The Diffie-Hellman Key Exchange protocol revolutionized cryptography by enabling secure key exchange over insecure channels, forming the basis for many secure communication protocols used today. However, it’s essential to implement it with proper authentication measures to safeguard against potential vulnerabilities.