[[8- Secure Channels]] 

> Galois/Counter Mode (GCM) is a widely used encryption mode that provides both confidentiality and data integrity. It is often used in combination with block ciphers like **AES** (AES-GCM).

> GCM is particularly notable for its efficiency and performance, especially in hardware implementations. Let's explore its key aspects:

### Overview of Galois/Counter Mode (GCM)

1. **Combination of Modes**:
   - GCM combines the Counter (CTR) mode for encryption with the Galois mode for authentication.
   - CTR mode encrypts plaintext blocks using a block cipher and a counter, ensuring fast and parallelizable operations.
   - Galois mode provides a Message Authentication Code (MAC) for data integrity and authentication.

2. **Components**:
   - **Block Cipher**: AES is the most common cipher used with GCM.
   - **Initialization Vector (IV)**: A unique value used for each encryption operation. It should not be reused with the same key.
   - **Plaintext**: The data to be encrypted.
   - **Authentication Tag**: A short piece of data used to authenticate the encrypted message and any associated data.

### How GCM Works

1. **Encryption**:
   - GCM encrypts plaintext using the CTR mode. The [[Cipher Block Chaining (CBC)]] (like AES) encrypts a counter and [[nonce]] (derived from the IV), and the output is XORed with the plaintext to produce ciphertext.
   - The counter is incremented for each block of data.

2. **Authentication**:
   - GCM generates an authentication tag using the [[Galois field multiplication]]. It combines the ciphertext and any additional authenticated data (AAD) with a hash subkey derived from the encryption key.
   - This tag ensures the integrity and authenticity of both the encrypted data and the AAD.

3. **Decryption**:
   - The process reverses the encryption steps. The CTR mode decrypts the ciphertext.
   - The integrity of the data is verified by recalculating and comparing the authentication tag.

### Advantages

- **Efficiency**: GCM is efficient in both software and hardware implementations. It allows for parallel processing, speeding up encryption and decryption operations.
- **Security**: Offers strong confidentiality and integrity protection.
- **Flexibility**: Can handle AAD, which is authenticated but not encrypted, useful for scenarios where some data (like headers) need integrity but not confidentiality.

### Applications

- **TLS and SSL**: For securing web traffic.
- **VPN Protocols**: Such as in IPsec for secure internet connections.
- **Disk Encryption**: To protect data at rest with integrity checking.

### Considerations

- **IV/Nonce Management**: It's crucial to never reuse an IV with the same encryption key, as this can compromise security.
- **Authentication Tag Size**: The size of the tag can be configured, trading off between performance and security.
