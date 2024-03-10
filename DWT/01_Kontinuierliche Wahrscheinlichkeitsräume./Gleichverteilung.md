[[Grundlagen_Kontinuierlich|Grundlagen_Kontinuierlich]].

- Bei einer Gleichverteilung sind alle möglichen Werte innerhalb eines bestimmten Intervalls gleich wahrscheinlich.
- Die Wahrscheinlichkeitsdichtefunktion (PDF) der Gleichverteilung für das Intervall $[a, b]$ ist wie folgt definiert: $$f(x) = \begin{cases} \frac{1}{b-a} & \text{für } a \leq x \leq b \\ 0 & \text{sonst} \end{cases}$$
- Die kumulative Verteilungsfunktion (CDF) der Gleichverteilung für das Intervall $[a, b]$ ist wie folgt definiert: $$F(x) = \int_{-\infty}^xf(t)dt= Pr[X\leq x]= \begin{cases} 0 & \text{für } x < a \\ \frac{x-a}{b-a} & \text{für } a \leq x \leq b \\ 1 & \text{für } x > b \end{cases}$$

### Erwartungswert:
Der Erwartungswert $E[X]$ einer Gleichverteilung auf $[a, b]$ ist der **Durchschnitt der beiden Endpunkte** des Intervalls und wird wie folgt berechnet: $$E[X] = \frac{a+b}{2}$$
### Varianz:
Die Varianz $Var[X]$ einer Gleichverteilung auf $[a, b]$ wird wie folgt berechnet: $$\text{Var}[X] = \frac{(b-a)^2}{12}$$

