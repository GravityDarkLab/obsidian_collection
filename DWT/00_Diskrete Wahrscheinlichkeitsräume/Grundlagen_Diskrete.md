
## Diskreter Wahrscheinlichkeitsraum:

- Eine diskreter Wahrscheinlichkeitsraum ist durch eine Ergebnismenge ==$\Omega=\{\omega_1,\omega_2,...\}$== von **Elementarereignissen** gegeben.

- Jedem **Elementarereignis** $\omega_i$ ist eine Elementarwahrscheinlichkeit $Pr[\omega_i]$ zugeordnet, wobei wir fordern, dass $$0 ≤ Pr[\omega_i] ≤ 1$$ und      $$\sum_{\omega \in \Omega} Pr[\omega] =1$$
- Eine Menge E ⊆ Ω heißt **Ereignis**. Die Wahrscheinlichkeit $Pr[E]$ eines Ereignisses ist durch $$Pr[E]:=\sum_{\omega\in\Omega}Pr[\omega]$$ definiert.

## Komplementäres Eriegnis:

- $\bar{E}$ heißt komplementäres Eriegnis zu E und $Pr[\bar{E}]=1-Pr[E]$.

## Regeln:
- Wenn $A \cap B = \emptyset$ , dann A und B sind **==disjunkt==**.

$$\text{relative Häufigkeit von E}:= \frac{\text{absolute Häufigkeit von E}}{\text{Anzahl aller Beobachtungen}} = \frac{\text{Anzahl Eintreten von E}}{\text{Anzahl aller Beobachtungen}} = \frac{|E|}{|\Omega|}$$

- Wenn $A\subseteq B$, so folgt $Pr[A]\leq Pr[B]$.

#### Additionssatz:
- Wenn die Ereignisse $A_1, . . . , A_n$ **paarweise disjunkt** sind, so folgt: $$Pr[\bigcup_{i=1}^{n}A_i]=\sum_{i=1}^n Pr[A_i]$$
#### Siebformel:
![[Pasted image 20230429121722.png]]
$$\begin{aligned} P(A \cup B) &= P(A) + P(B) - P(A \cap B) \ \end{aligned}$$ $$\begin{aligned} P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(A \cap B) - P(A \cap C) - P(B \cap C) + P(A \cap B \cap C) \end{aligned}$$
#### Boolesche Ungleichung:
$$Pr[\bigcup_{i=1}^n A_i]\leq\sum_{i=1}^n Pr[A_i]$$


Weiter zu:
- **[[Bedingte Wahrscheinlichkeiten]]**.
- **[[Zufallsvariablen]]**.
	- [[Erwartungswert E 𝞵]].
	- [[Varianz V 𝞼²]].
	- [[Momenten einer Zufallsvariablen]].
	- [[Indikatorvariable]].
	- [[Bernoulli-Verteilung]].
	- [[Binomialverteilung]].
	- [[Geometrische Verteilung]].
	- [[Poisson-verteilung]].
- [[Coupon-Collector-Problem]].
- [[Abschätzen von Wahrscheinlichkeiten]]:
	- [[Markov]].
	- [[Chebyshev]].
	- [[Gesetz der großen Zahlen]].
	- [[Chernoff-Schranken]].
- [[Erzeugende Funktionen]].
- [[Momenterzeugende Funktionen]].


