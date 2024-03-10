Related to [[1- Introduction]].

```
This attacker can intercept, modify, or fabricate any network message, knows all protocols, but cannot crack strong cryptography directly. It's a tool for designing and testing cryptographic protocols under the assumption of facing the most powerful possible adversary, ensuring the system's resilience
```

- The attacker **is** or **owns** the network (all routers, switches, connections)
> **BUT**: The attacker has no control over end systems.

- The attacker can perform any active and passive attack
>**BUT**: The attacker cannot break cryptographic primitives (encryption, signing, hashing, etc.)
>
>**CAUSE**: 
>- The cryptographic primitives are secure.
>- The nodes that participate in the cryptographic protocol are secure.

- When we try to break a protocol, we do this on the layers of the cryptographic protocol.
- When we try to mitigate a vulnerability, we do this on the layers of the cryptographic protocol.