[[Abschätzen von Wahrscheinlichkeiten]].

- The Law of Large Numbers is a fundamental concept in probability theory and statistics.
- It states that as the sample size increases, the average of a sequence of independent and **==identically distributed random variables==** <u>approaches the expected value of those variables</u>.

	``In other words, the sample mean becomes increasingly close to the population mean as more observations are taken``.

### There are two main versions of the Law of Large Numbers:
#### 1. Weak Law of Large Numbers:
The Weak Law of Large Numbers, also known as **Bernoulli's Law of Large Numbers**, states that for a sequence of independent and identically distributed random variables $X1, X2, ..., Xn$ with a common mean $μ$, the sample mean $Z = (X1 + X2 + ... + Xn) / n$ converges in probability to the population mean $μ$ as the sample size $n$ approaches infinity. Mathematically, it can be represented as:
$$\lim_{{n \to \infty}} Pr\left(\left|\frac{{X_1 + X_2 + \ldots + X_n}}{{n}} - \mu\right| < \epsilon\right) = 1$$

#### 2. Strong Law of Large Numbers:
The Strong Law of Large Numbers states that for a sequence of independent and identically distributed random variables $X1, X2, ..., Xn$ with a common mean $μ$, the sample mean $Z = (X1 + X2 + ... + Xn) / n$ converges almost surely to the population mean $μ$ as the sample size n approaches infinity. Mathematically, it can be represented as:
$$Pr\left(\lim_{{n \to \infty}} \frac{{X_1 + X_2 + \ldots + X_n}}{{n}} = \mu\right) = 1$$
![[Pasted image 20230528162925.png]]
![[Pasted image 20230528163029.png]]
