
- Im Kontext diskreter Wahrscheinlichkeiten wird eine Erzeugende Funktion oft als eine Potenzreihe definiert. Angenommen, wir haben eine diskrete Zufallsvariable X, die Werte in einer Menge von nicht-negativen ganzen Zahlen annimmt. Die Erzeugende Funktion G_X(t) von X ist definiert als: $$G_X(t) = \sum_{k=0}^{\infty}Pr[X=k].t^k = E[t^X]$$wobei $E[.]$ den Erwartungswert bezeichnet. Das bedeutet, dass $G_X(t)$ den Erwartungswert von $t^X$ angibt.

- Durch Ableitungen und andere Operationen mit der Erzeugenden Funktion lassen sich verschiedene Momente der Verteilung berechnen.
	- Zum Beispiel ist der $$E[X] = G_X'(1)$$ (die Ableitung der Erzeugenden Funktion an der Stelle $t=1$).
	- und die $$Var[X] = G_X''(1) + G_X'(1) - [G_X'(1)]^2$$

## Konvergenz:
![[Pasted image 20230601102441.png]]


## Beobachtung:
Sei $Y:=X+t$ mit $t\in \mathbb{N}_0$. Dann gilt: $$G_Y(s)=\mathbb{E}[s^Y]=\mathbb{E}[s^{X+t}]=\mathbb{E}[s^t.s^X]=s^t\mathbb{E}[s^X]=s^t.G_X(s)$$

- $$G_X'(0)=Pr[X=1]$$
- $$G_X^{(i)}(0)=Pr[X=i].i! \Rightarrow \frac{G_X^{(i)}(0)}{i!}=Pr[X=i]$$
> Die Dichte und die Verteilung einer Zufallsvariablen X mit $W_X ⊆ N$ sind durch ihre wahrscheinlichkeitserzeugende Funktion **==eindeutig==** bestimmt.

## Beispiele:
- [[Bernoulli-Verteilung]]:
	- ![[Pasted image 20230601104009.png]]
- [[Gleichverteilung]]:
	- ![[Pasted image 20230601104035.png]]
- [[Binomialverteilung]]:
	- ![[Pasted image 20230601104058.png]]
- [[Geometrische Verteilung]]:
	- ![[Pasted image 20230601104119.png]]
- [[Poisson-verteilung]]:
	- ![[Pasted image 20230601104137.png]]