---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Monte Carlo/Proof of Validity of Metropolis-Hastings Algorithm.md"
ingested: 2026-06-09
---

The [[Metropolis-Hastings Algorithm]] constructs a Markov Chain that has [[Markov Transition Kernel]] given by:
$$
\mathcal{P}(x,A)=r(x)\delta_{x}(A)+\int_{A}\alpha(x,y)q(x,y)dy
$$
where
$$
\alpha(x,y)=\min\left\{  \frac{\pi(y)q(y,x)}{\pi(x)q(x,y)},1  \right\}
$$
is the acceptance probability, and
$$
r(x)=\int(1-\alpha(x,y))q(x,y)dy
$$
is the rejection probability.

We can easily show that $\mathcal{P}$ satisfies the detailed balance equations:
$$
\begin{align}
\int_{A}\mathcal{P}(x,B)\pi(dx) & =\int_{A}\left( r(x)\delta_{x}(B)+\int_{B}\alpha(x,y)q(x,y)dy \right)\pi(x)dx \\
 & =\int_{A}r(x)\delta_{x}(B)\pi(x)dx+\int_{A}\int_{B}\alpha(x,y)q(x,y)\pi(x)dydx \\
 & =\int_{B}r(x)\delta_{x}(A)\pi(x)dx+\int_{A}\int_{B}\alpha(y,x)q(y,x)\pi(y)dydx \\
& =\int_{B}r(x)\delta_{x}(A)\pi(x)dx+\int_{B}\int_{A}\alpha(x,y)q(x,y)\pi(x)dydx \text{ (change of variables)}\\
 & =\int_{B}\mathcal{P}(x,A)\pi(dx)
\end{align}
$$

where
$$
\delta_{x}(A)=\begin{cases}
1, & x \in A \\
0, & x \notin A
\end{cases}
$$