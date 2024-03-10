[[Grundlagen_Kontinuierlich|Grundlagen_Kontinuierlich]].

$$X \sim \mathcal{N}(\mu, \sigma^2)$$

- The normal distribution, also known as the Gaussian distribution or bell curve, is a continuous probability distribution that is symmetric and characterized by its mean and standard deviation. It is one of the most important probability distributions in statistics and is widely used in various fields.

### PDF:
- The probability density function (PDF) of the normal distribution is given by the following equation: $$f(x) = \frac{1}{\sqrt{2\pi \sigma^2}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}$$
- The normal distribution is often denoted as $X \sim \mathcal{N}(\mu, \sigma^2)$, where $\sim$ denotes "is distributed as" and $\mathcal{N}$ represents the normal distribution.

### Cumulative distribution function (CDF):
$$F(x)=\frac{1}{\sqrt{2\pi \sigma^2}} . \int_{-\infty}^xexp({-\frac{(t-\mu)^2}{2\sigma^2})}dt =: \phi(x;\mu,\sigma)$$
> Diese Funktion heißt **Gauß´sche $\phi-\text{Funktion}$**.
> $X \sim \mathcal{N}(0, 1)$ heißt **Standardnormalverteilung**.

> Sei X eine beliebige $X \sim \mathcal{N}(\mu, \sigma^2)$ und $Y:=\frac{X-\mu}{\sigma}$. dann heißt $Y$ normiert und ferner gilt: $$Pr[a<X\leq b]= Pr[\frac{a-\mu}{\sigma}<Y\leq \frac{b-\mu}{\sigma}] = \phi(\frac{b-\mu}{\sigma})-\phi(\frac{a-\mu}{\sigma})$$
> ![[Pasted image 20230615121016.png]]

![[Pasted image 20230612120053.png]]


#### Lineare Transformation der Normalverteilung:
- Für ein beleibiges $Y=aX+b$ mit $X \sim \mathcal{N}(\mu, \sigma^2)$ gilt $$Y \sim \mathcal{N}(a\mu+b, a^2\sigma^2)$$
#### Additivität der Normalverteilung:
- Sei die Zufallsvariablen $X_1, . . . , X_n$ unabhängig und normalverteilt mit den Parametern $μ_i$, $σ_i$ $(1 ≤ i ≤ n)$. Es gilt: Die Zufallsvariable $Z := a_1X_1 + . . . + a_nX_n$ ist normalverteilt mit Erwartungswert $μ = a_1μ_1 + . . . + a_nμ_n$ und Varianz $σ^2 = a^2_1 σ_1^2 + . . . + a^2_nσ_n^2$.
- [[Zufallsvariablen#Faltungssatz für $Z=X+Y$]].
![[Bildschirmfoto 2023-06-19 um 12.16.07.png]]

## Normalverteilung als Grenzwert der Binomialverteilung
- [[Zentraler Grenzwertsatz#Grenzwertsatz von de Moivre]] ermöglicht, die Normalverteilung als Grenzwert der Binomialverteilung aufzufassen. 
> Die folgende Aussage ist eine Konsequenz von [[Zentraler Grenzwertsatz#Grenzwertsatz von de Moivre]]:
> 	Sei $H_n\sim Bin(n,p)$ eine Binomialverteilte Zufallsvariable.
> 	Die Verteilung von $H_n/n$ konvergiert für $n\to\infty$ gegen $\mathcal{N}(p,p(1-p)/n)$.  


