[[Induktive Statistik]].

- Stichproben.
- Stichprobenvariablen.
- Je mehr Experimente wir also durchführen, umso genauere und zuverlässigere Aussagen können wir über den zugrunde liegenden Wahrscheinlichkeitsraum ableiten.


- Gegeben sei eine Zufallsvariable $X$ mit der Dichte $f(x;θ)$. Eine Schätzvariable oder kurz Schätzer für den Parameter $θ$ der Dichte von $X$ ist eine Zufallsvariable, die **==aus mehreren (meist unabhängigen und identisch verteilten) Stichprobenvariablen==** $X_i$ zusammengesetzt ist.
- Ein Schätzer $U$ heißt **==erwartungstreu==**, wenn gilt: $$\mathbb{E}[U]=\theta$$
- $\mathbb{E}[U-\theta]$ nennt man **==Bias==** der Schätzvariablen $U$.
> Bei erwartungstreuen Schätzvariablen ist der Bias gleich Null.



## Erwartungstreuer Schätzer für E[\X]\: 

![[Pasted image 20230626123044.png]]

- Der Schätzer $\overline{X}$ ist also ein **erwartungstreuer** Schätzer für den Erwartungswert von X. Ein wichtiges Maß für die Güte eines Schätzers ist die **==mittlere quadratische Abweichung (mean squared error)==**, kurz **==MSE==**. Diese berechnet sich durch $$MSE:=\mathbb{E}[(U-\theta)^2]\text{. Wenn U erwartungstreu ist!}$$
so folgt: $$MSE:=\mathbb{E}[((U-\mathbb{E}[U])^2]=Var[U]$$
> Wenn die Schätzvariable A eine ==**kleinere MSE**== besitzt als die Schätzvariable B, so sagt man, dass A **==effizienter==** ist als B ist. 
> Eine Schätzvariable heißt **==konsistent==** im quadratischen Mittel, wenn $MSE → 0$ für $n → ∞$ gilt. Hierbei bezeichne $n$ den **Umfang der Stichprobe**.
- **Schwache Konsistenz**:
![[Pasted image 20230626124950.png]]
für $n → ∞$ liegen die Werte von $X$ beliebig nahe am gesuchten Wert $θ = E[X]$. Diese Eigenschaft nennt man auch schwache Konsistenz , da sie aus der Konsistenz im quadratischen Mittel folgt.


## Erwartungstreuer Schätzer für Var[\X]\: 
![[Pasted image 20230626125421.png]]
> $S^2$ ist eine erwartungstreue Schätzvariable für die Varianz von X.


## Stichprobenmittel bzw. Stichprobenvarianz:
![[Pasted image 20230626125608.png]]


- [[Maximum-Likelihood-Schätzer]].