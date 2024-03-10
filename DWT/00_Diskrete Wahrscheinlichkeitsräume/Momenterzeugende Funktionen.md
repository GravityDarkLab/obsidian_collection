- Die Momenterzeugende Funktion $M_X(t)$ einer Zufallsvariable $X$ ist definiert als: $$M_X(t) = E[e^{tX}] = E[\sum_{i=0}^{\infty}\frac{(Xt)^i}{i!}]=\sum_{i=0}^{\infty}\frac{E[X^i]}{i!}.t^i$$
wobei $E[.]$ den Erwartungswert bezeichnet. Das bedeutet, dass $M_X(t)$ den Erwartungswert von $e^{tX}$ angibt.

Auch: $$M_X(t)=\mathbb{E}[e^{Xt}]=E[(e^t)^X]=G_X(e^t)$$

- Die Momente können wie folgt aus der Momenterzeugenden Funktion abgeleitet werden:
	- Das $k$-te Moment von $X$ ist gegeben durch $M_X^{(k)}(0)$, wobei $M_X^{(k)}(0)$ die $k$-te Ableitung der Momenterzeugenden Funktion an der Stelle $t=0$ ist.
	- Der ==**Erwartungswert**== von $X$ ist das erste Moment und entspricht $M_X'(0)$.
	- Die ==**Varianz**== von X ist das zweite zentrale Moment und entspricht $M_X''(0) - [M_X'(0)]^2$.


## Satz: Zufällige Summen

- Seien $X_1, X_2, . . .$ **==unabhängige==** und **==identisch==** verteilte Zufallsvariablen mit der wahrscheinlichkeitserzeugenden Funktion $G_X(s)$. 
- N sei ebenfalls eine **==unabhängige==** Zufallsvariable mit der wahrscheinlichkeitserzeugenden Funktion $G_N(s)$. Dann besitzt dieZufallsvariable $Z:=X_1+...+X_N$ die wahrscheinlichkeitserzeugende Funktion $G_Z(s) = G_N(G_X(s))$.


## Beobachtung:
![[Pasted image 20230601105626.png]]



## Beispiele:
![[Pasted image 20230601105733.png]]
