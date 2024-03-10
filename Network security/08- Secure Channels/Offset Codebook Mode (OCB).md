Offset Codebook Mode (OCB) is an advanced mode of operation for block ciphers, designed to provide both **encryption** and **authentication** (a==uthenticated encryption==) efficiently.
It's known for its high performance and minimalistic design.

### Key Features of OCB Mode

1. **Authenticated Encryption**: OCB mode provides both encryption and message authentication in a single step. This dual functionality ensures data confidentiality and integrity.
2. **Efficiency**: OCB is designed for high performance. It is faster than other authenticated encryption modes like CCM (Counter with [[CBC-MAC]]) and GCM ([[Galois - Counter Mode (GCM)]]), especially in environments where both encryption and authentication are needed.
3. **Low Overhead**: OCB has **minimal overhead** for both short and long messages, making it suitable for a variety of applications, including those where bandwidth or storage is at a premium.

### How OCB Works

1. **Initialization**: OCB begins with an initialization vector ($IV$) and a unique [[nonce]] $n$. **==Nonces must never be reused with the same key==**.

2. **Encryption and Authentication Process**:
   - A unique offset is computed for each block of the plaintext, using the [[nonce]] and block counter.
   - The plaintext block is XORed with the offset, then encrypted.
   - After encryption, the ciphertext block is XORed again with the offset.
   - Additionally, a checksum is computed for the plaintext, which is combined with the final block’s encryption to produce an authentication tag.

3. **Decryption Process**: 
   - Decryption follows the reverse process. Ciphertext blocks are XORed with the offset, decrypted, and XORed again with the offset to produce the plaintext.
   - A checksum is calculated for the decrypted plaintext and compared with the authentication tag to verify the integrity of the message.

### Applications of OCB Mode

- **Network Security**: Used in protocols where both encryption and authentication are required, such as in secure file transfer protocols.
- **Wireless Communication**: Suitable for environments where computational resources and bandwidth are limited.
- **Disk Encryption**: Effective for encrypting data on storage devices due to its efficiency and low overhead.
