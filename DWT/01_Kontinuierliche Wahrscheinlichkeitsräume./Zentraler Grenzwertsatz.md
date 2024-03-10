- Die Zufallsvariablen $X_1,...,X_n$ besitzen jeweils dieselbe Verteilung und seien unabhängig. Erwartungswert und Varianz von $X_i$ existieren für $i=1,...,n$ und seien mit $\mu$ und $\sigma^2$ bezeichnet. Die Zufallsvariablen $Y_n$ seien definiert durch $Y_n := X_1 + . . . + X_n$ für $n ≥ 1$. Dann folgt, dass die Zufallsvariablen $$Z_n:=\frac{Y_n-n\mu}{\sigma\sqrt{n}}$$ ==**asymptotisch standardnormalverteilt**== sind, also $Z_n ∼ N (0, 1)$ für $n → ∞$. $$\lim_{x \to +\infty} F_n(x)=\phi(x)\text{ für alle x}\in \mathbb{R}$$
- ![[Bildschirmfoto 2023-06-19 um 11.06.31.png]]
> Ein wichtiger Spezialfall das Zentralen Grenzwertsatzes besteht darin, dass die auftretenden Zufallsgrößen [[Bernoulli-Verteilung]] sind.

## Grenzwertsatz von de Moivre:
- $X_1, . . . , X_n$ seien unabhängige Bernoulli-verteilte ([[Bernoulli-Verteilung]]) Zufallsvariablen mit gleicher Erfolgswahrscheinlichkeit $p$. Dann gilt für die Zufallsvariable $H_n$ mit $$H_n:=X_1+...+X_n$$ für $n \geq 1$, dass die Verteilung der Zufallsvariablen $$H_n^*:= \frac{H_n-np}{\sqrt{np(1-p)}}$$ für $n\to\infty$ gegen die Standradnormalverteilung konvergiert.
- --> [[Normalverteilung#Normalverteilung als Grenzwert der Binomialverteilung]].


![[Bildschirmfoto 2023-06-19 um 11.26.06.png]]


## Verschiedene Approximationen der Binomialverteilung:
[[Binomialverteilung]].
- ![[Bildschirmfoto 2023-06-19 um 11.30.03.png]]
> **Beispiel**:![[Bildschirmfoto 2023-06-19 um 11.31.18.png]]
> ![[Bildschirmfoto 2023-06-19 um 11.31.34.png]]

#### Stetigkeitskorrektur:
Bei der Approximation der Binomialverteilung mit Hilfe von Korollar 109 führt man oft noch eine so genannte **==Stetigkeitskorrektur==** durch. Zur Berechnung von $Pr[X ≤ x]$ füt $X ∼ Bin(n, p)$ setzt man:  
![[Bildschirmfoto 2023-06-19 um 11.33.16.png]]

- **Approximation durch die Poisson-Verteilung**:
	- ![[Bildschirmfoto 2023-06-19 um 11.34.55.png]]
- **Approximation durch die Chernoff-Schranken**:
	- ![[Bildschirmfoto 2023-06-19 um 11.35.39.png]]
- **Approximation durch Normalverteilung**:
	- ![[Bildschirmfoto 2023-06-19 um 11.36.30.png]]
