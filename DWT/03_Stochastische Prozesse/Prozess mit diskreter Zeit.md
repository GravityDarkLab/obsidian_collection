## Markov chains:
- Markov chains are models used to describe situations where what happens next only depends on the current situation, not on the past.
- You have different states and transitions between them with associated probabilities. You use a transition matrix to represent these probabilities. Markov chains help predict long-term behavior and solve exercises involving probabilities of reaching states or expected number of transitions.
- ![[Pasted image 20230716140500.png]]


#### Wahrscheinlichkeitsraum einer Markov-Kette:
Nehmen wir an, dass wir die Kette von der Zeit 0 bis zur Zeit $t_0$ beobachten wollen. Wir bezeichnen die Folge von Zuständen, die von der Kette in dieser Zeit durchlaufen wurde, mit$w=\vec{x}=(x_0, x_1, . . . , x_{t0})$.  $$Pr[w]=(q_0)_{x_0}.\prod_{i=1}^{t_0}Pr[X_i=x_i|X_{i-1}=x_{i-1}]$$
![[Pasted image 20230716141558.png]]

#### Berechnung von Übergangswahrscheinlichkeiten:
Dafür benutzen wir eine Matrixschreibweise:
- $q_t=q_0.P^t$.
- $q_{t+1}=q_t.P$.
- $q_{t+k}=q_t.P^k$.

- Eine Matrix $P$ ist diagonalisierbar, wenn es eine invertierbare Matrix $B$ und eine Diagonalmatrix $D$ gibt, so dass $P = BDB^{-1}$, wobei $D$ die Diagonalmatrix ist und die **==Diagonalelemente die Eigenwerte von A sind==**. [[Matrix]].
- Dann gilt: $P^k=BD^kB^{-1}$.


### Eigenschaften:
	- Transient: Zustand wird nicht mehr besucht. f_i<1
	- Rekkurent: Zustand wird immer wieder besucht. f_i=1
	- Wenn eine Zustand absorbierend ist dann ist auch rekkurent.
	- Wir bezeichnen einen Zustand i als absorbierend, wenn aus ihm keine Übergänge herausführen, d.h. p_ij = 0 für alle j != i und folglich p_ii = 1.
	- Eine Markov-Kette heißt irreduzibel, wenn es für alle Zustandspaare i,j ein zahl n gibt, sodass p_ij > n --> Graph stark zusammenhämgend und hat eine eindeutige Pi.

![[Pasted image 20230716174523.png]]
![[Pasted image 20230716174551.png]]

	- Periode 𝜁 = ggt(alle pfade von i nach i)
	- Eine Zustand mit 𝜁=1 heißt aperiodisch.
	- Eine Markov-Kette is aperiodisch, falls alle ihre Zustände aperiodisch sind.
	- Ein Zustand i ∈ S einer endlichen Markov-Kette ist sicherlich dann aperiodisch, wenn er im Übergangsdiagramm:
		- eine Schleife besitzt.
		- auf mind. 2 geschlossene Wegen liegt deren länge Teilfremd ist (ggt(W_1,W_2)=1)
		- Irreduzible, aperiodische Markov-Ketten nennt man ergodisch.
		- Ergodisch --> Konvergiert gegen ein Pi.

- [[Aperiodizität]].
-  [[Doppeltstochastische Matrizen]].

### Ankunftswahrscheinlichkeiten und Übergangszeiten:
- **Übergangszeit**:
	- $$T_{ij}:=min\{n\geq 0| X_n=j, \text{ wenn }X_0=i\}$$
	- zählt die Anzahl der Schritte, die von der Markov-Kette für den Weg von $i$ nach $j$ benötigt werden. $T_{ij}$ nennen wir die Übergangszeit (engl. hitting time) vom Zustand $i$ zum Zustand $j$. 
	> Wenn $j$ nie erreicht wird, setzen wir $T_{ij} = ∞$.
> fall $i=j$ dann $T_{ii}=h_{ii}=0$ und $f_{ii}=1$.

- **Rückkehrzeit ; Rückkehrwahrscheinlichkeit**:
	- ![[Pasted image 20230716151232.png]]

### Übergangs-/Rückkehrzeiten:
- ![[Pasted image 20230716151555.png]]

### Ankunfts-/Rückkehrwahrscheinlichkeiten:
- ![[Pasted image 20230716151646.png]]


![[Pasted image 20230716153151.png]]


### Stationäre Verteilung:
- Wenn eine Markov-Kette eine stationäre Verteilung besitzt, bedeutet dies, dass die Wahrscheinlichkeiten, in jedem Zustand zu sein, sich nicht mehr ändern, wenn das System weiterhin läuft und sich entwickelt. Die stationäre Verteilung stellt somit eine stabile Verteilung der Zustände dar.

- Formal ausgedrückt: Eine stationäre Verteilung einer Markov-Kette ist ein Vektor π, der die Bedingung erfüllt: $π = π * P$.

- ![[Pasted image 20230716173745.png]]

> Nicht alle Markov-Ketten haben ein eine stationäre Verteilung.
> ![[Pasted image 20230716173914.png]]