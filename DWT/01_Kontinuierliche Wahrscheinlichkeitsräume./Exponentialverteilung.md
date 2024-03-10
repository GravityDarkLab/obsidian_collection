- Die Exponentialverteilung mit Parameter $λ$, oft als $Exp(λ)$ bezeichnet, hat die folgende Wahrscheinlichkeitsdichtefunktion (PDF): $$f_X(x)=\begin{cases}\lambda e^{-\lambda x} & \text{für } x \geq 0 \\ 0 & \text{für } x < 0 \end{cases}$$
- Der Parameter λ, auch als Rateparameter bezeichnet, bestimmt die Form und Skalierung der Verteilung. Es ist der Kehrwert des mittleren Ereignisintervalls oder der **==erwarteten Wartezeit zwischen den Ereignissen==**.

- Die kumulative Verteilungsfunktion (CDF) der Exponentialverteilung lautet: $$F_X(x)=\begin{cases}1 - e^{-\lambda x} & \text{für } x \geq 0 \\ 0 & \text{für } x < 0 \end{cases}$$
### Gedächtnislosigkeit:
> Die Exponentialverteilung hat die Eigenschaft der **==Gedächtnislosigkeit==**, was bedeutet, dass die Wahrscheinlichkeit, dass ein Ereignis in den nächsten Zeitintervall eintritt, ==unabhängig von der vergangenen Wartezeit ist==. 
> Diese Eigenschaft macht sie nützlich für Modelle, bei denen Ereignisse in diskreten Zeitschritten eintreten können.

![[Pasted image 20230612121211.png]]



## Erwartungswert & Varianz:
$$\mathbb{E}[X]=\frac{1}{\lambda}$$
$$\mathbb{E}[X^2]=\frac{2}{\lambda^2}$$
$$\mathbb{Var}[X]=\mathbb{E}[X^2]-\mathbb{E}[X]^2=\frac{1}{\lambda^2}$$
### Skalierung:
- Sei $Y=aX$ mit $X\sim Exp(\lambda)$.
	- $Y\sim Exp(\frac{\lambda}{a})$.

### Anwendungen der Exponentialverteilung:
- **Zuverlässigkeitsanalysen**: 
	Die Exponentialverteilung wird verwendet, um die **==Ausfallzeiten von Systemen zu modellieren==** und die Zuverlässigkeit von Komponenten und Systemen zu analysieren.
    
- **Warteschlangentheorie** --> [[Warteprobleme mit der Exp(λ)]] : 
	Die Exponentialverteilung wird verwendet, um die Wartezeiten in Warteschlangenmodellen zu modellieren, z.B. um die **durchschnittliche Wartezeit** in einem Kundendienstzentrum oder die Servicezeit an einem Schalter zu berechnen.
    
- **Lebensdauerverteilungen**:
	Die Exponentialverteilung wird verwendet, um die **==Lebensdauer von Produkten oder Geräten zu modellieren==**, insbesondere ==**wenn die Lebensdauer nicht von der Zeit abhängt**==.
    
- **Analyse von Poisson-Prozessen**:
	Die Exponentialverteilung ist eng mit dem **Poisson-Prozess** verbunden, bei dem Ereignisse in diskreten Zeitschritten auftreten. ==Die Exponentialverteilung modelliert die Zeitspannen zwischen den Ereignissen in einem Poisson-Prozess==.


## Exponentialverteilung als Grenzwert der geometrischen Verteilung:
							[[Exponentialverteilung]] & [[Geometrische Verteilung]].
							
Die Beziehung zwischen der geometrischen Verteilung und der Exponentialverteilung ergibt sich, **==wenn die Erfolgswahrscheinlichkeit der geometrischen Verteilung sehr klein wird==** und die **==Anzahl der Versuche sehr groß wird==**. In diesem Grenzfall geht die geometrische Verteilung zur Exponentialverteilung über.