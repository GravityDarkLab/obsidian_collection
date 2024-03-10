[[Abschätzen von Wahrscheinlichkeiten]].

The Chebyshev inequality is another important probability inequality that provides an upper bound on the probability of a random variable deviating from its mean by a certain amount. It is applicable to any random variable with a finite variance and is derived from the concept of variances.
 $$P(|X-\mu| \geq t) \leq \frac{\sigma^2}{{t^2}} = P(|X-\mu| \geq t\sigma) \leq \frac{1}{{t^2}} $$

### Example 1:
Suppose we have a random variable $X$ representing the height of individuals, with a mean height $\mu = 170$ cm and a variance $\sigma^2 = 25$ cm$^2$. We want to find an **==upper bound==** on the probability that an individual's height deviates from the mean **==by at least 2 standard deviations ==**($t = 2$). Using the Chebyshev inequality, we can write: $$P(|X - 170| \geq 2\sqrt{25}) \leq \frac{1}{4}$$
Therefore, the Chebyshev inequality tells us that the probability of an individual's height deviating from the mean by at least 2 standard deviations is less than or equal to $\frac{1}{4}$

### Example 2:
Wir werfen 1000-mal eine faire Münze und ermitteln die Anzahl $X$ der Würfe, in denen ”Kopf“ fällt. X ist Binomialverteilt mit $X \sim Bin(1000, p = 12 )$, also gilt: $\mathbb{E}[X]=\frac{1}{2}n=500$ und $\mathbb{Var}[X]=\frac{1}{4}n=250$.
- **Wie groß ist die Wahrscheinlichkeit, dass mehr als 550-mal ”Kopf“ fällt ?**
	- ==Gesucht ist eine Abweichung von 550-500=50 von E(X)==.
	- $$Pr[X>550]\leq Pr[|X-500|>50]\leq\frac{250}{50^2}=0,1$$