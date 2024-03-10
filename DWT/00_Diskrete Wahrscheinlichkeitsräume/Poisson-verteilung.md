[[Zufallsvariablen]].

$$X\sim Po(\lambda)$$

- The Poisson distribution is a discrete probability distribution that models the number of events that occur within a fixed interval of time or space. It is often used to describe rare events that occur independently with a known average rate.
- The Poisson distribution is characterized by a single parameter, denoted by $λ$ (lambda), which represents the average rate of events per interval.
- The probability mass function (PMF) of the Poisson distribution is given by:$$P(X = k) = f_x(k)=\frac{e^{-\lambda} \cdot \lambda^k}{k!}$$
- For the Mean (Expected Value): $$E(X) = \lambda$$
- For the Variance: $$Var(X) = \lambda$$

![[Pasted image 20230527181656.png]]

## Poisson-Verteilung als Grenzwert der Binomialverteilung:
										[[Poisson-verteilung]] & [[Binomialverteilung]].

> The Poisson distribution can be considered as a limiting case of the Binomial distribution under certain conditions. Specifically, when the number of trials, denoted by "n," is large and the probability of success, denoted by "p," is small, the Binomial distribution approaches the Poisson distribution.
> To be more precise, if we have a Binomial distribution with parameters "n" (number of trials) and "p" (probability of success), and we let "n" tend to infinity while keeping the product "$np$" constant, then the Binomial distribution converges to the Poisson distribution with parameter $λ = np$.
> Mathematically, the relationship between the Binomial and Poisson distributions can be stated as follows:
> 	As n approaches infinity, while $np$ approaches a finite value $λ$, the probability mass function of the Binomial distribution converges to the probability mass function of the Poisson distribution: $$b(k,n,p)= P(X = k) = \binom{n}{k} \cdot p^k \cdot (1 - p)^{n-k} \rightarrow e^{-\lambda}\frac{\lambda^k}{k!}$$
> 	$X\sim Bin(n,\lambda/n)$ sich für $n \rightarrow \infty$ der Poisson-Verteilung $Po(\lambda)$ anhärt.
> 	

![[Pasted image 20230527184822.png]]


## Summe von Poisson-verteilten Zufallsvariablen:
![[Pasted image 20230527185009.png]]
![[Pasted image 20230527185034.png]]