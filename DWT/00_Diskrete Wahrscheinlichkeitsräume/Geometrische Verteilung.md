[[Zufallsvariablen]].

$$X\sim Geo(p)$$

- The geometric distribution is a discrete probability distribution that models the **==number of trials needed to achieve the first success==** in a sequence of independent Bernoulli trials ([[Bernoulli-Verteilung]]), where each trial has a constant probability of success, denoted by "p".

 - Geometric Distribution Probability Mass Function (PMF):
	 - $$P(X = i)=f_x(i)= p(1 - p)^{i-1}$$
- $$E(X) = \frac{1}{p}$$
- $$Var(X) = \frac{1 - p}{p^2}$$
### Gedächtnislosigkeit:
$$Pr[X>x]=(1-p)^x$$
 ![[Pasted image 20230527171116.png]]
$$Pr[X>y+x|X>x]=Pr[X>y]$$

### Negativ binomialverteilt:

- Sei die n **==unabhängige und geometrisch verteilt Zufallsvariablen== $X_1\cdot \dots \cdot X_n$** und $Z=X_1+\dots + X_n$, damit bezeichnet Z also die Anzahl der versuche bis zum n-ten erfolgreichen Experiement. Falls $Z=z$ ist, so werden also genau $n$ erfolgreiche und $z-n$ nicht erfolgreiche Experiemente durchgeführt. Dafür gibt es genau $\binom{z-1}{n-1}$ Möglichkeiten, von denen jede mit Wahrscheinlichkeit $p^n(1-p)^{z-n}$ eintritt: $$f_Z(z)=\binom{z-1}{n-1}p^n(1-p)^{z-n}$$ 