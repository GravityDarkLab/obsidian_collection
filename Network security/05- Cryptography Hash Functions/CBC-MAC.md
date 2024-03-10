- **What It Is**: A technique that uses a block cipher (like AES) in Cipher Block Chaining (CBC) mode for message authentication.
- **How It Works**:
    1. The message is divided into blocks.
    2. Each block is encrypted with a block cipher, using the previous block's ciphertext as an input (chain), along with a secret key.
    3. The final block's output is used as the MAC.
- **Properties**:
    - **Fixed-Length Output**: The output length is determined by the block cipher's block size.
    - **Block Chaining**: Makes it secure against simple attacks, but has vulnerabilities if used improperly (e.g., same IV for multiple messages).