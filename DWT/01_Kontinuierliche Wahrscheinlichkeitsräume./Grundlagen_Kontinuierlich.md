- Eine **kontinuierliche** oder auch **==stetige==** Zufallsvariable $X$ und ihr zugrunde liegender kontinuierlicher (reeller) Wahrscheinlichkeitsraum sind definiert durch eine **==integrierbare Dichte(-funktion)==** $f_X : R → R^+_0$ mit der Eigenschaft: $$f(x) \geq 0 \quad \text{für alle } x \in (-\infty, \infty)$$ $$\int_{-\infty}^{\infty} f(x) \, dx = 1$$
- Die Wahrscheinlichkeit, dass die kontinuierliche Zufallsvariable $(X)$ einen bestimmten Wert in einem Intervall $[a, b]$ annimmt, kann durch die Integration der $PDF$ über dieses Intervall berechnet werden: $$P(a \leq X \leq b) = \int_{a}^{b} f(x) \, dx$$
## Wichtige stetige Verteilungen:
- **[[Gleichverteilung]]**.
- **[[Normalverteilung]]**.
- **[[Exponentialverteilung]]**.
- **[[Mehrere kontinuierlich Zufallsvariablen]]**.



## Eigenschaften:
- $F_X$ ist **==monoton steigend==**.
- $F_X$ ist **==stetig==**. Man spricht daher auch von einer ”**==stetigen Zufallsvariablen==**“. Es gilt: $\\lim_{x \to -\infty} F_X(x) = 0$ und $\lim_{x \to \infty} F_X(x) = 1$.
- Jeder (**außer an endlich vielen Punkten**) differenzierbaren Funktion $F$ , welche die zuvor genannten Eigenschaften erfülllt, können wir eine Dichte $f$ durch $f(x) = F'(x)$ zuordnen. und es gilt: $$Pr[a<X ≤b]=F_X(b)−F_X(a)$$
![[Pasted image 20230605080858.png]]

## Axiome:
- **[[Kolmogorov-Axiome und σ-Algebren]]**.
- **[[Messbare Funktionen]]**.

## Weitere Themen:
- [[Rechnen mit kontinuierlichen Zufallsvariablen]].
- [[Simulation von Zufallsvariablen]].
- [[Erwartungswert und Varianz]].
- [[Summen von Zufallsvariablen]].

- **[[Poisson-Prozess]]**.

- [[Momenterzeugende Funktionen für Kontinuierliche Zufallsvariabeln]].
- [[Zentraler Grenzwertsatz]].
