- $$\text{Zufallsvariable:}\;\;\;\;\;\;X: \Omega \to \mathbb{R}$$
- Beispiel: 
	- Wir werfen eine ideale Münze drei Mal. Als Ergebnismenge erhalten wir $\Omega:=\{H,T\}^3$. Die Zufallsvariable Y bezeichne die Gesamtanzahl der  Würfe mit Ergebnis ”Head“.
	- Beispielsweise gilt also Y (HTH) = 2 und Y (HHH) = 3. Y hat den Wertebereich $W_Y = \{0,1,2,3\}$.


## Dichtefunktion $f(x) := f_X$ :
$$f_X:x\in \mathbb{R} \to Pr[X=x]\in[0,1]$$


## Gemeinsame Dichte $f(X,Y):=f_{X,Y}$ :
$$f_{X,Y}(x,y):=Pr[X=x,Y=y]$$
- #### Randdichten:
$$f_X(x)=\sum_{y\in W_Y}f_{X,Y}(x,y) \;\;\text{bzw.}\; \; f_Y(y)=\sum_{x\in W_X}f_{X,Y}(x,y)$$


## Verteilungsfunktion $F(X):=F_X$ :
$$F_X:x\in\mathbb{R}\to Pr[X\leq x]=\sum_{x'\in W_X:x'\leq x}Pr[X = x']\in [0,1]$$

## Gemeinsame Verteilung $F(X,Y):=F_{X,Y}$ :

![[Pasted image 20230513190905.png]]

- #### Randverteilung:
![[Pasted image 20230513191030.png]]


## Bedingte Zufallsvariable $f_{X|A}$:
$$f_{X|A}(x):=Pr[X=x|A]=\frac{Pr[X=x \cap A]}{Pr[A]}$$

## Unabhängigkeit:

![[Pasted image 20230513191701.png]]
![[Pasted image 20230513192805.png]]
 ![[Pasted image 20230513192854.png]]


## Faltungssatz für $Z=X+Y$ :
- Für 2 **==unabhängige==** Zufallsvariablen $X$ und $Y$ sei $Z:=X+Y$. Es gilt $$f_Z(z)=\sum_{x\in W_X}f_X(x).f_Y(z-x)$$


## Indikatorvariable:
- [[Indikatorvariable]].


## Erwartungswert $\mu$ :
- **[[Erwartungswert E 𝞵]]**.

## Varianz $\sigma^2$ :
- **[[Varianz V 𝞼²]]**.

## Wichtige diskrete Verteilungen:
- **[[Bernoulli-Verteilung]]**.
- **[[Binomialverteilung]]**.
- **[[Geometrische Verteilung]]**.
- **[[Poisson-verteilung]]**.
- [[Coupon-Collector-Problem]].

## Bemerkung:
- **Hypergeometrisch verteilt**:
![[Pasted image 20230513183125.png]]



