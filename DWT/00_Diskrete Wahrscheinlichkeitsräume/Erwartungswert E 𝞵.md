
- [[Zufallsvariablen]].

> Erstens **==muss==** $\sum_{x\in W_X}|x| \cdot Pr[X=x]$ **==konvergieren==**.

$$\mathbb{E}:= \sum_{x\in W_X}x \cdot Pr[X=x] = \sum_{x\in W_X}x \cdot f_x(x)$$
- Sein X und Y Zufallsvariablen über dem Wahrscheinlichkeitsraum $\Omega$ mit $X(\omega)\leq Y(\omega)$ für alle $\omega \in \Omega$. Dann gilt $\mathbb{E}[X]\leq \mathbb{E}[Y]$. Daraus folgt insbesonders, dass $a\leq \mathbb{E}[X] \leq b$ gilt, wenn für die Zufallsvariable X die Eigenschaften  $a\leq X(w) \leq b$ für alle $\omega \in \Omega$ erfüllt ist.

### Rechenregeln:
- ##### Linearität:
	- $\mathbb{E}[aX+b]=a\cdot \mathbb{E[X]}+b$.
	- ![[Pasted image 20230513193507.png]]
	- $\mathbb{E}[X]=\sum_{i=1}^\infty Pr[x \geq i]$.
- **Multiplikativität**: 
	- $\mathbb{E}[X_1\cdot \dots \cdot X_n]=\mathbb{E}[X_1]\cdot\dots\cdot\mathbb{E}[X_n]$.
	- ****==Unabhängigkeit==** ist **==notwendig==****.

### Bendingte Erwartungswert:
- $$\mathbb{E}[X|A]=\Sigma_{x\in W_x}x\cdot f_{X|A}(x)$$
	- ==Für paarweise disjunkte Ereignisse $A_1,\dots,A_n$ gilt==:
	- $$\mathbb{E}[X|A]=\Sigma_{i=1}^{n}\mathbb{E}[X|A_i]\cdot Pr[A_i]$$

- Für **==unabhängige==** Zufallsvariablen $X_1,...,X_n$ gilt: $$\mathbb{E}[X_1\cdot \dots \cdot X_n]=\mathbb{E}[X_1]\cdot\dots\cdot\mathbb{E}[X_n]$$
- Der Erwartungswert und die Varianz gehören zu den so genannten [[Momenten einer Zufallsvariablen]].