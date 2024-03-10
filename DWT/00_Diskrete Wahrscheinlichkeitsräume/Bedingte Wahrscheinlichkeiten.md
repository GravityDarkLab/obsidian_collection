
- $Pr[B|B]=1$.
- $Pr[A|\Omega]=Pr[A]$.
- $Pr[A|B]=\frac{Pr[A\cap B]}{Pr[B]}$.
- $Pr[\emptyset|B]=0$.
- $Pr[\bar{A}|B]=1-Pr[A|B]$.
- $Pr[A\cap B]=Pr[B|A]\cdot Pr[A]=Pr[A|B]\cdot Pr[B]$.
- $Pr[\bar G \cap \bar H] = Pr[\bar G] - Pr[\bar G \cap H] = Pr[\bar G]  - (Pr[H]-Pr[G \cap H])$. 
- **Multiplikationssatz**:
	- ![[Pasted image 20230429123854.png]]
- **Satz von der ==totalen Wahrscheinlichkeit==**: Die Ereignisse $A_1,...,A_n$ seien paarweise disjunkt und es gelte $B \subseteq A_1∪...∪A_n$. Dann folgt: $$Pr[B]=\sum_{i=1}^n Pr[B|A_i].Pr[A_i]$$
- **==Satz von Bayes==**: $$Pr[A_i|B]=\frac{Pr[A_i\cap B]}{Pr[B]}=\frac{Pr[B|A_i]\cdot Pr[A_i]}{\sum_{j=1}^n Pr[B|A_j].Pr[A_j]}$$
- Zwei Ereignisse A und B heißen **unabhängig**, wenn gilt $$Pr[A \cap B]=Pr[A].Pr[B]$$
> Es folgt auch, dass für zwei unabängige Ereignisse A und B auch die Erignisse $\bar{A}$ und $B$ auch $A$ und $\bar{B}$ bzw. $\bar{A}$ und $\bar{B}$.

- Seien A, B und C unabhängige Ereignisse. Dann sind auch $A\cap B \cap C$ bzw $(A \cup B)\cap C$ unabhängig. 

### Beispiel:
![[Pasted image 20230429122955.png]]



# Problems: 
- [[2 Kids Problem]].
- [[Goat Problem]].
- [[Birthday Problem]].