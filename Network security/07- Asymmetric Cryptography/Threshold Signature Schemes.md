[[7-Asymmetric Cryprography]].
[[Diffie-Hellman key exchange protocol]].

#### Identified challenges with classical public key cryptography
- What if the $K_{sec}$ key gets compromised?
- What if the node that stores $K_{sec}$ is not available or gets destroyed?
- What if we need **more than one entity to sign**, think "==distributed system=="?

#### Approach
- Distribute $K_{sec}$ into $n$ shares (The corresponding $K_{pub}$ is not distributed).
- Each $K_{sec}$ share is stored on an individual node
- Threshold signature schemes requires $t$ out of $n$ nodes to be active during the signing

#### Threshold signature schemes solve above challenges
- Attacker needs to compromise t nodes to compromise the $K_{sec}$.
- If at least $t$ nodes remain functional, a signature can be computed – availability
- Each node can decide if it wants to participate in the signing process

### Key Concepts

1. **Key Sharing**: The secret key is divided into multiple shares. This process is often achieved using techniques like Shamir's Secret Sharing.
2. **Threshold**: A predetermined number (the threshold) is set, below which the combined shares cannot construct the key or sign a document.
3. **Signing Process**: To create a valid signature, a minimum number of participants, equal to or greater than the threshold, must combine their key shares.
#### How It Works

1. **Initialization**: A trusted party generates the secret key and uses a secret sharing scheme to divide it into shares.
	1. Trusted setup – relies on (centralized) trusted 3rd party
	2. Untrusted setup – Distributed Key Generation (DKG)
2. **Distribution**: These shares are securely distributed to the participants.
3. **Signing**: When a signature is needed, the participants provide their shares. If enough shares (meeting the threshold) are present, the signature can be generated.
4. **Verification**: The resulting signature is verified using the public key, similar to standard digital signature verification processes.

### Applications

- **Secure Transactions**: Used in financial institutions for authorizing high-value transactions.
- **Distributed Systems**: Ensures no single point of failure in systems like blockchain or distributed ledgers.
- **Organizational Security**: Allows for shared control over critical operations, preventing abuse of power by any single entity.
- Variety of interesting use-cases:
	- Cryptographic wallets
	- Public key infrastructure ([[PKI]])
	- Byzantine Fault Tolerant (BFT) protocols
- Many threshold signature schemes for various signature families e.g., ECDSA, BLS, Schnorr 

### Benefits

- **Enhanced Security**: Difficult for an attacker to compromise the key since they would need to access multiple shares.
- **Risk Mitigation**: Reduces the risk of a single point of failure or abuse of authority.
- **Flexibility**: Can be tailored to different organizational structures and requirements.
- Threshold signature ensures $K_{sec}$ Confidentiality.
- Allows for better availability and distribution of power among involved parties.