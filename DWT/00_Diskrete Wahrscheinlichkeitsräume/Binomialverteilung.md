[[Zufallsvariablen]].


- Die Binomialverteilung ist eng mit der [[Bernoulli-Verteilung]] verbunden. Sie wird verwendet, um **==die Anzahl der Erfolge in einer bestimmten Anzahl von unabhängigen Bernoulli-Experimenten zu modellieren==**.

> Die Binomialverteilung beschreibt nun die **Anzahl der Erfolge** (zum Beispiel Kopf beim Münzwurf) in einer bestimmten Anzahl von unabhängigen Bernoulli-Experimenten ([[Bernoulli-Verteilung]]).

- $$X\sim Bin(n,p)$$
- Die Binomialverteilung wird oft durch zwei Parameter beschrieben: n und p
	- $n$: Anzahl der unabhängigen Experimente an, die durchgeführt werden.
	- $p$ gibt die Wahrscheinlichkeit für einen Erfolg in einem einzelnen Experiment an.

- Die Wahrscheinlichkeitsfunktion für die Binomialverteilung lautet: $$P(X = x)=f_X(x):=b(x,n,p)= \binom{n}{x} \cdot p^x \cdot q^{n-x}$$
- $$\mathbb{E}[X]=np$$ $$\mathbb{Var}[X]=npq=np(1-p)$$
> Wenn $X\sim Bin(n_x,p)$ und $Y\sim Bin(n_y,p)$ **==unabhängig==** sind, dann gilt für $Z:=X+Y$, dass $Z\sim Bin(n_x+n_y,p)$


To: [[Zentraler Grenzwertsatz#Verschiedene Approximationen der Binomialverteilung]].
