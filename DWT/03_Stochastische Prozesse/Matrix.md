
## Eigenwerte und Eigenvektoren:

- Um Eigenwerte und Eigenvektoren einer Matrix zu bestimmen, folgt hier eine grundlegende Vorgehensweise:
1. **Berechne die charakteristische Gleichung**:
	- Die charakteristische Gleichung einer Matrix A wird durch $det(A - λI) = 0$ dargestellt.
	- Löse die charakteristische Gleichung: Um die Eigenwerte zu bestimmen, löse die charakteristische Gleichung det(A - λI) = 0 nach λ auf. 
2. Berechne die Eigenvektoren: Für jeden Eigenwert λ, setze ihn in die Gleichung $(A - λI)v$ = 0 ein, wobei $v$ ein Vektor ist. Löse das Gleichungssystem $(A - λI)v = 0$, um den Eigenvektor $v$ zu erhalten. **Beachte, dass v nicht der Nullvektor sein darf**.


## Inversdarstellung:
Leider ist nicht jede beliebige **Matrix** **invertierbar**, sondern nur solche **Matrizen**, die bestimmte Voraussetzungen erfüllen. Es stellt sich also die Frage, **wann ist eine Matrix invertierbar**? Dazu musst du prüfen, ob du eine ==**quadratische Matrix** ==vorliegen hast und ob die ==**Determinante** ==der **Matrix** ungleich Null ist.
- $A = \begin{bmatrix} a & b \\ c & d \\ \end{bmatrix}$:
	- $\text{{det}}(A) = |A| = ad - bc$.
	- $A^{-1}=\frac{1}{ad - bc}\begin{bmatrix} d & -b \\ -c & a \end{bmatrix}$

- ![[Pasted image 20230716144752.png]]
	- ![[Pasted image 20230716144834.png]]
	- ![[Pasted image 20230716144946.png]]
	- 

