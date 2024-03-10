[[Zufallsvariablen]].

- The Coupon-Collector Problem is a classic problem in probability theory that involves collecting a complete set of different coupons or items. The problem is named after the analogy of collecting coupons from a series of randomly distributed identical boxes.

- Assumptions:
	1.  There are "n" different types of coupons available.
	2.  Each time you obtain a coupon, it is equally likely to be any one of the "n" types.
	3.  You collect coupons one at a time, and each collection is independent.
- Objective: The goal is to determine how many coupons you need to collect on average in order to have at least one of each type.
	- Let's denote the random variable representing the number of coupons collected until obtaining a complete set as $X$. We want to find the expected value $\mu$ or mean of X, denoted by $\mathbb{E}[X]$.
	- To analyze this problem, let's consider the probability of collecting the first coupon, the second coupon, and so on:
		- On the first trial, you don't have any coupons. So, the probability of obtaining a new coupon is 1 (since any coupon will be new). **Therefore, the expected number of trials to get the first coupon is 1**.
		- On the second trial, you already have one coupon. The probability of obtaining a new coupon is $(\frac{n-1}{n})$ (since there are $(n-1)$ remaining types of coupons that you still need). Therefore, the expected number of additional trials to get the second coupon is $\frac{n}{n-1}$.
		- Similarly, on the third trial, you already have two coupons. The probability of obtaining a new coupon is $(\frac{n-2}{n})$. Therefore, the expected number of additional trials to get the third coupon is $\frac{n}{n-2}$.
		- In general, on the $k-th$ trial (where $k$ is between $1$ and $n$), you already have $(k-1)$ coupons. The probability of obtaining a new coupon is $\frac{n-(k-1)}{n}$. Therefore, the expected number of additional trials to get the kth coupon is $\frac{n}{n-(k-1)}$.
		> $X_k$ ist geometrisch verteilt mit $p=\frac{n-k+1}{n}$ und es gilt $\mathbb{E}[X_k]=\frac{n}{n-k+1}$.
		
- To find $\mathbb{E}[X]$, we sum up the expected number of trials for each coupon:
	- ![[Pasted image 20230527175339.png]]

With $H(n)$ as the harmonic series . However, there isn't a closed-form expression for $H(n)$. As "n" grows large, $H(n)$ approaches $ln(n) + O(1)$. Therefore, we can approximate the expected value of X as: $$\mathbb{E}[X] ≈ n * ln(n) + O(n)$$

