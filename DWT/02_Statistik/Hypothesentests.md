## Definition eines Tests:
- $K:=\{\vec{x}\in \mathbb{R}^n;\; \vec{x}\text{ führt zur Ablehnung der Hyphothesen}\}$, is **Ablehnungsbereich** oder **kritischen Bereich** des Tests genannt.
- Gewöhnlich wird K konstruiert, indem man die Zufallsvariablen $X_1, . . . , X_n$ zu einer neuen Variablen $T$ , der so genannten Testgröße, zusammenfasst. Dann unterteilt man den Wertebereich $R$ von $T$ in mehrere Bereiche, die entweder zur Ablehnung der Hypothese führen sollen oder nicht. Dabei betrachtet man meist ein einzelnes halboffenes oder abgeschlossenes Intervall und spricht dann von einem **==einseitigen==** bzw. von einem **==zweiseitigen==** Test.![[Pasted image 20230701120827.png]]
> Die zu überprüfende Hypothese bezeichnen wir mit $H_0$ und sprechen deshalb auch von der **Nullhyphotese**.
> $H_1$ ist die **Alternative**.


## Fehler bei statistischen Tests:
### Fehler 1. Art / $\alpha-Fehler$ / Signifikanzniveau des Tests:
- $H_0$ gilt, wird aber abgelehnt. $$\alpha=\sup_{p\in H_0}Pr[X\in K]=\sum_{k \in K}Pr_{p_0}[x=k]$$

### Fehler 2. Art / $\beta-Fehler$:
- $H_0$ wird nicht abgelehnt obwohl $H_1$ gilt ($H_0$ wird akzeptiert obwohl sie nicht gilt). $$\sum_{k \notin K}Pr_{p_1}[x=k]$$


> $\alpha-Fehler$ und $\beta-Fehler$ minimal halten $\Rightarrow$ $\alpha\leq\beta$. 


## Gütefunktion:
- Die so gennante Gütefunktion g gibt allgemein die Wahrscheinlichkeit an, mit der ein Test die Nullhypothese verwirft.
- $$g(p) = Pr_p(t\in K)$$


## Verfahren:
- Wie findet man das richtige Testverfahren?
	- **Anzahl der beteiligten Zufallsgrößen**:
	Sollen **==zwei Zufallsgrößen==** mit potentiell unterschiedlichen Verteilungen verglichen werden, für die jeweils eine Stichprobe erzeugt wird (**[[Zwei-Stichproben-Test]]**), oder wird nur eine <u>einzelne Zufallsgröße</u> untersucht (<u>Ein-Stichproben-Test</u>)?
	- **Formulierung der Nullhypothese**:
	Welche Größe dient zur Definition der Nullhypothese? Hierbei werden in erster Linie Tests unterschieden, die Aussagen über verschiedene so genannte Lageparameter treffen, wie z.B. den Erwartungswert oder die Varianz der zugrunde liegenden Verteilungen.
	
	> Im Zwei-Stichproben-Fall könnte man beispielsweise untersuchen, ob der Erwartungswert der Zufallsgröße A größer oder kleiner als bei Zufallsgröße B ist. Gelegentlich wird zur Formulierung der Nullhypothese auch der so genannte Median betrachtet: Der Median einer Verteilung entspricht dem (kleinsten) Wert x mit F (x) = 1/2.	
 
	 - **Annahmen über die Zufallsgrößen**:
Was ist über die Verteilung der untersuchten Größe(n) bekannt? Bei entsprechenden Annahmen könnte es sich z.B. um die Art der Verteilung, den Erwartungswert oder die Varianz handeln.

##### Was wird getestet ?

- Erwartungswert $\mu$ ?
		- if($\sigma$){
		[[Gaußtest]]();
		} else {
		[[t-Test]]();
		}  

- Wahrscheinlichkeit $Pr[x]$ ?
		- if($X \sim Bern(p)$){
		[[Binomial-Test]]();
		} else {
		[[𝜒²-Anpassungstest]]();
		}  