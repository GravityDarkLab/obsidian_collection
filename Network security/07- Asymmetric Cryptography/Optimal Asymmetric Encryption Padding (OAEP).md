[[7-Asymmetric Cryprography]].

Optimal Asymmetric Encryption Padding (OAEP) is a padding scheme often used in conjunction with RSA encryption. It's designed to enhance the security of RSA by preventing certain attacks that could be effective against plain RSA encryption.

### Background
- **RSA Encryption**: RSA is an asymmetric cryptographic algorithm that relies on the difficulty of factoring large numbers. However, plain RSA (without padding) can be vulnerable to various attacks, including chosen-plaintext and ciphertext attacks.
- **Need for Padding**: Padding schemes like OAEP are used to add additional data to the plaintext before encryption, reducing the predictability of the input and increasing security.

### How OAEP Works
1. **Plaintext Processing**: Before encryption, the plaintext message is processed as follows:
   - **Message**: A message `M` that needs to be encrypted.
   - **Random Seed**: A random seed is generated. This randomness is crucial for security.
   - **Two Functions**: OAEP uses two cryptographic hash functions, typically denoted as G and H.
   - **Padding**: The message is padded with some extra bits to ensure that its length matches the RSA modulus size.

2. **OAEP Encoding**:
   - The message `M` is combined with some padding to create a padded message.
   - The random seed is expanded using the G function and XORed with the padded message.
   - The result of this XOR is then processed with the H function and XORed with the random seed.
   - The final output of this process is a data block that has the same length as the RSA modulus and is ready to be encrypted using RSA.

3. **Encryption**: The RSA algorithm then encrypts this data block.

### Security Benefits
- **Randomization**: OAEP introduces randomness into the encryption process, which makes it difficult for attackers to exploit patterns in the plaintext.
- **Mitigation of Attacks**: It helps prevent several types of attacks on RSA, including chosen-plaintext and chosen-ciphertext attacks.

### Implementation
- OAEP is often used in protocols and standards that require RSA encryption, like in certain implementations of TLS/SSL for securing internet communications.
- It's important that the same padding scheme (like OAEP) is used for both encryption and decryption.


### Example: Encoding and Decoding a Message `X` with OAEP

#### 1. Encoding (Padding) Process
Suppose you want to encrypt the message `X` using RSA with OAEP. Here are the steps:

1. **Initial Setup**:
   - **Plaintext (`X`)**: This is your original message.
   - **Random Seed (`r`)**: Generate a random seed. For example, `r = "random_seed"`.
   - **Padding String (`PS`)**: A padding string, which could be a series of zeros, for example. Its length varies to ensure that `X` + `PS` is the right length for the RSA modulus.
   - **G and H Functions**: Two hash functions (or similar operations). For simplicity, let's call them `G` and `H`.

2. **OAEP Padding**:
   - **Step 1**: `X` is concatenated with `PS`: `X||PS`.
   - **Step 2**: Use `G` to expand `r`: `G(r)`. 
   - **Step 3**: XOR `G(r)` with `X||PS`: `paddedX = G(r) XOR X||PS`.
   - **Step 4**: Apply `H` to `paddedX`: `H(paddedX)`.
   - **Step 5**: XOR `H(paddedX)` with `r`: `finalPad = H(paddedX) XOR r`.

3. **RSA Encryption**:
   - Encrypt `finalPad` using the RSA encryption algorithm. This encrypted data is what gets transmitted.

#### 2. Decoding (Unpadding) Process

Upon receiving the encrypted data, the recipient (who knows `r` and has the RSA private key) will perform these steps:

1. **RSA Decryption**:
   - Decrypt the received data using the RSA decryption algorithm to get `finalPad`.

2. **OAEP Unpadding**:
   - **Step 1**: XOR `finalPad` with `r` to retrieve `H(paddedX)`.
   - **Step 2**: Apply `H` to `H(paddedX)` to get back `paddedX`.
   - **Step 3**: XOR `paddedX` with `G(r)` (since `G(r)` is known) to retrieve `X||PS`.
   - **Step 4**: Separate `X` from `PS`.

3. **Retrieve Original Message**:
   - The recipient now has the original plaintext message `X`.

![[Pasted image 20240113124537.png]]