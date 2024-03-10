## Erwartungswert:
Der Erwartungswert einer kontinuierlichen Zufallsvariable X mit Wahrscheinlichkeitsdichtefunktion (PDF) f(x) ist definiert als: $$E[X] = \int_{-\infty}^{\infty} x \cdot f(x) \, dx$$ sofern das Integral $\int_{-\infty}^{\infty}|x|.f_X(x)dx$ endlich ist.



## Varianz:
Die Varianz einer kontinuierlichen Zufallsvariable $X$ mit Erwartungswert $μ$ ist definiert als: $$\text{Var}[X] = E[(X - \mu)^2] = \int_{-\infty}^{\infty} (x - \mu)^2 \cdot f(x) \, dx$$ wenn $E[(X - \mu)^2]$ existiert!


#### Lemma:
- Sei X eine kontinuierliche Zufallsvariable, und sei $Y :=g(X)$. Dann gilt $$E[Y] = \int_{-\infty}^{\infty} g(x) \cdot f_X(x) \, dx$$
- 