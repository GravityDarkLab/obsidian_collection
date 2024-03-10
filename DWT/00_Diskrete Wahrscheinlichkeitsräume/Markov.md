[[Abschätzen von Wahrscheinlichkeiten]].

- The Markov inequality is a fundamental probability inequality that provides an **==upper bound==** on the probability of a random variable being greater than or equal to a positive constant. It is applicable to non-negative random variables and is derived from the concept of expectations.
- It states that for a non-negative random variable X and any positive constant "$a$", the probability that X is greater than or equal to "$a$" can be **==bounded==** by the ratio of the **==expected value of X to "a"==**: $$Pr(X \geq a) \leq \frac{{E[X]}}{{a}}$$ $$\mathbb{Pr}[X\geq a\cdot \mathbb{E}[X]]\leq \frac{1}{a}$$
### Steps:
1. Start with a non-negative random variable X ≥ 0
2. Choose a positive constant $a>0$.
3. The Markov inequality states that $P(X \geq a) \leq \frac{{E[X]}}{{a}}$.
4. The expected value of a random variable X (denoted by $\mathbb{E}[X]$) is calculated as the **sum of the product of each possible value of X with its corresponding probability** ([[Erwartungswert E 𝞵]]).


### Example:
Suppose we have a non-negative random variable $X$ representing the number of hours a student spends studying each day. Let's assume that the expected value of $E(X)$ is 4 hours.
	$\rightarrow$  We want to find an upper bound on the probability that the student studies for at least 8 hours in a day ($P(X ≥ 8)$).
	- Using the Markov inequality, we can write: $$P(X \geq 8) \leq \frac{{E(X)}}{{8}} = \frac{{4}}{{8}} = \frac{{1}}{{2}}$$
	- Therefore, the Markov inequality tells us that the probability of the student studying for at least 8 hours in a day is less than or equal to 1/2.
