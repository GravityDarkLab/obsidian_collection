- [[#Basic Concept of Chosen-Plaintext Attacks|Basic Concept of Chosen-Plaintext Attacks]]
- [[#Chosen-Plaintext Attacks in RSA|Chosen-Plaintext Attacks in RSA]]
- [[#How RSA Mitigates CPA Risks|How RSA Mitigates CPA Risks]]
- [[#General Defense Against CPA|General Defense Against CPA]]

### Basic Concept of Chosen-Plaintext Attacks

1. **Attacker's Capability**: The attacker can choose arbitrary plaintexts and obtain their corresponding ciphertexts. They don't need to know the secret key used for encryption.
2. **Information Gathering**: By analyzing these plaintext-ciphertext pairs, the attacker tries to deduce either the secret key or some information about other encrypted messages.
### Chosen-Plaintext Attacks in RSA

In RSA, a chosen-plaintext attack might proceed as follows:

1. **Collect Data**: The attacker gathers several plaintext-ciphertext pairs. These pairs are generated using the public key, which is known.
2. **Mathematical Analysis**: The attacker uses these pairs to perform a mathematical analysis. Since RSA is deterministic (the same plaintext will always result in the same ciphertext when encrypted with the same key), if the attacker encrypts a known plaintext, they can compare it to an intercepted ciphertext to check for matches.
3. **Key Deduction**: The ultimate aim could be to deduce the private key, but this is extremely difficult with RSA if it's properly implemented with large key sizes. More realistically, the attacker might seek patterns or weaknesses in the encryption process.
    

### How RSA Mitigates CPA Risks

- **Key Size**: Large key sizes make it computationally infeasible to deduce the private key through brute-force.
- **Padding Schemes**: Modern RSA implementations use padding schemes like OAEP (Optimal Asymmetric Encryption Padding) which add randomness to the encryption process, making RSA non-deterministic and more secure against these attacks.

### General Defense Against CPA

- **Randomization**: Introducing randomness in the encryption process can significantly mitigate the risk of CPAs.
- **Limiting Access**: Restricting the ability to obtain ciphertexts for chosen plaintexts can also be a defensive measure, though this isn't always practical.