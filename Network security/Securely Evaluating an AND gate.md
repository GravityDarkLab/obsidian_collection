[[14.2- Secure Multiparty Computation]].

1. **Garbling the AND Gate**: The party creating the garbled circuit (let's call them Alice) encrypts the truth table of the AND gate. Each row of the truth table corresponds to a possible input combination (00, 01, 10, 11), and each is ==encrypted with a unique key==.

2. **Input Encoding**: Alice assigns two encrypted keys for each input bit to the other party (let's call them Bob), one representing 0 and the other 1. ==However, she does not tell Bob which key corresponds to which value==.

3. **Computation**: Bob selects the keys corresponding to his inputs (without knowing what values they represent) and uses them to decrypt the garbled truth table of the AND gate. The design of the garbled circuit ensures that Bob can only decrypt the row corresponding to the correct input combination, thus obtaining the result of the AND operation without learning anything about Alice's input or revealing his input.

### Secret Sharing Approach

See Also [[Secret Sharing]].

Secret sharing involves splitting each input into "shares" that are distributed among the parties. The shares are designed so that the original inputs can be reconstructed only when a sufficient number of shares are combined. Here's how an AND gate could be evaluated:

1. **Share Distribution**: Each input bit (from Alice and Bob) is split into shares. For simplicity, let's say each bit is split into two shares.

2. **Computing Shares of AND Gate**: Alice and Bob compute shares of the output of the AND gate using their input shares. This involves operations defined by the secret sharing scheme that mimic the logic of an AND gate.

3. **Combining Shares**: After computing the output shares of the AND gate, Alice and Bob exchange their output shares and combine them to obtain the final result of the AND operation.


![[Screenshot 2024-02-12 at 20.43.59.png]]