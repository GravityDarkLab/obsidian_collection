- **Randomness** can be described by unpredictability, and unpredictability is good for security, as an attacker cannot predict a secret key.
- A mesure for unpredictability in **entropy**. $$H(x)=-\sum_x(P(X=x).log_2P(X=x))$$ where $P(X=x)$ is the probability for $X=x$
- **Entropy is maximized for a uniform distribution**.
![[Pasted image 20240103230139.png]]

## Cryptographically Secure Pseudo Random Number Generator (CSPRNG)
- The length of the seed should be large enough to make brute-force search over all seeds infeasible.
- The output should be indistinguishable from truly random sequences
- No polynomial-time algorithm can correctly distinguish between an output sequence of the generator and a truly Random sequence
- The output should be unpredictable for an attacker with limited resources, without knowledge of the seed
- No polynomial-time algorithm can predict the next bit of the generator with probability > 0.5 ("next-bit test")