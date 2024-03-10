[[Grundlagen_Kontinuierlich|Grundlagen_Kontinuierlich]].

## Die Kolmogorov-Axiome:
  
- Die Kolmogorov-Axiome sind grundlegende Prinzipien in der Wahrscheinlichkeitstheorie:
	- **Nicht-Negativität**: Die Wahrscheinlichkeit eines Ereignisses ist immer größer oder gleich Null. $$P(A) \geq 0 \text{ für alle Ereignisse } A$$
	- **Sicherheit**: Die Wahrscheinlichkeit des gesamten Grundraums ist eins. $$P(\Omega) = 1$$
	- **Additivität**: Für ==disjunkte== (ausschließende) Ereignisse ist die Wahrscheinlichkeit ihrer ==Vereinigung== gleich der Summe ihrer Einzelwahrscheinlichkeiten. $$P(\bigcup_{i=1}^\infty A_i) = \sum_{i=1}^\infty Pr[A_i]$$
- ![[Pasted image 20230605130341.png]]
## Die σ-Algebra:
- Eine σ-Algebra, auch σ-Algebra von Ereignissen genannt, ist eine Sammlung von Ereignissen, die bestimmte Eigenschaften erfüllt. Sie definiert die Menge der Ereignisse, auf denen Wahrscheinlichkeiten definiert sind.
- Eine σ-Algebra $\mathcal{F} \in \mathcal{P(\Omega)}$ erfüllt die folgenden Bedingungen:
	1. $\Omega$ ist ein Element von $\mathcal{F}$. 
	2. Wenn ein Ereignis $A$ in $\mathcal{F}$ enthalten ist, dann ist auch das Komplement $\overline{A}=\Omega \setminus A$ in $\mathcal{F}$ enthalten.
	3. Wenn eine abzählbare Menge von Ereignissen $A_1, A_2, A_3, \ldots$ in $\mathcal{F}$ enthalten ist, dann ist auch die Vereinigung $\bigcup_{i=1}^{\infty} A_i$ in $\mathcal{F}$ enthalten.
- Die σ-Algebra ermöglicht es, mathematische Operationen wie Vereinigung, Komplementbildung und Schnittbildung auf Ereignissen durchzuführen, für die Wahrscheinlichkeiten definiert sind. Sie bildet eine grundlegende Struktur für die Konstruktion von Wahrscheinlichkeitsräumen und die Durchführung von Wahrscheinlichkeitsberechnungen.
#### Beispiel:
- Betrachten wir die Menge $\mathcal{F} = \{\emptyset, \Omega, \{1, 2\}, \{3, 4, 5\}\}$ über der Grundmenge $\Omega = \{1, 2, 3, 4, 5\}$. Um zu zeigen, dass $\mathcal{F}$ eine $\sigma$-Algebra ist, müssen wir die folgenden Bedingungen überprüfen:
	1. Das sichere Ereignis $\Omega$ ist ein Element von $\mathcal{F}$. 
	2. Das Komplement von $\{1, 2\}$ ist $\{3, 4, 5\}$, und beide sind in $\mathcal{F}$ enthalten. 
	3. Die Vereinigung von $\{1, 2\}$ und $\{3, 4, 5\}$ ist $\{1, 2, 3, 4, 5\} = \Omega$, und sie ist ebenfalls in $\mathcal{F}$ enthalten.
- Da alle Bedingungen erfüllt sind, ist $\mathcal{F}$ eine $\sigma$-Algebra über der Grundmenge $\Omega$.