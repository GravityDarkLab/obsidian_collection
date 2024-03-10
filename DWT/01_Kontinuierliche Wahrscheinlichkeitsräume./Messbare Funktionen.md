[[Grundlagen_Kontinuierlich|Grundlagen_Kontinuierlich]].


- Messbare Funktionen sind Funktionen, die eine Verbindung zwischen zwei messbaren Räumen herstellen. Ein messbarer Raum besteht aus einer Menge und einer σ-Algebra ([[Kolmogorov-Axiome und σ-Algebren]]) über dieser Menge.

> Formell ausgedrückt: Seien $(X, Σ_X)$ und $(Y, Σ_Y)$ messbare Räume. Eine Funktion $f: X → Y$ wird als messbar bezeichnet, wenn das Urbild jedes messbaren Sets in $Y$ unter $f$ ein messbares Set in $X$ ist. Das bedeutet, dass für jedes $A$ in$ Σ_Y$ das Urbild $f^{(-1)}(A)$ in $Σ_X$ enthalten ist.

> Jede stetige Funktion ist messbar. Auch Summen und Produkte von messbaren Funktionen sind wiederum messbar.

> Jeder messbaren Funktion kann man ein Integral, das so genannte **==Lebesgue-Integral==**, geschrieben $\int f d \lambda$, zuordnen.

- eine Abbildung auf den Borel’schen Mengen, die die Eigenschaft der Kolmogorov-Axiome erf̈üllt. Gilt daher zusätzlich noch $Pr[R] = 1$, so definiert $f$ auf natürliche Weise einen Wahrscheinlichkeitsraum $(Ω, A, Pr)$, wobei $Ω = R$ und $A$ die Menge der Borel’schen Mengen ist.


### Überabzählbar:
Um zu zeigen, dass Ω uberabzählbar ist, versuchen wir eine injektive Abbildung von einer uberabzählbaren Menge auf Ω zu finden. 

- Beispiel: Münze unendlich oft werfen.
In unserem Fall bietet sich das Intervall $[0, 1)$ an, welches uberabzählbar viele reelle Zahlen enthält. Bekanntermaßen lässt sich jede reelle Zahl $r$ injektiv auf eine Dezimalbruchentwicklung abbilden. Im Intervall $[0, 1)$ entspricht eine solche Dezimalbruchentwicklung einer unendlichen
Sequenz der ganzen Zahlen zwischen 0 und 9, welche die Nachkommastellen von $r$ angibt. Kodieren wir nun jede Zahl zwischen 0 und 9 eindeutig durch ein Quadrupel der Ereignisse Kopf und Zahl, so erhalten wir eine unendliche Sequenz von Kopf und Zahl, die wir $r$ zuordnen können. Wir haben also eine injektive Abbildung von
$[0, 1)$ auf $Ω$ gefunden und somit gezeigt, dass Ω uberabzählbar ist.

