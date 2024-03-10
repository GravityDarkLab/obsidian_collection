- **What It Is**: Similar to CBC-MAC but designed to overcome some of CBC-MAC's limitations, particularly for messages of varying lengths.
- **How It Works**:
    1. The message is divided into blocks, with padding added to the last block if needed.
    2. **It employs a block cipher in a way similar to CBC-MAC but with modifications to the last block to securely handle variable lengths**.
    3. The final block's output is the CMAC.
- **Properties**:
    - **Improved Security**: More secure for messages of different lengths.
    - **Block Cipher-Based**: Typically uses AES.