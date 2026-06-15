---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Monte Carlo/Metropolis-Hastings Algorithm.md"
ingested: 2026-06-09
---

Given a probability density $\pi$ called the *target distribution* defined on a state space $\mathcal{X}$, the Metropolis-Hastings algorithm proposes a generic way to construct a [[Markov Chain]] on $\mathcal{X}$ that is [[Ergodic]] and [[Stationary]] with respect to $\pi$; that is, the Markov chain returned by the algorithm converges to $\pi$. *Note that the existence of a stationary distribution for a Markov chain implies that it is [[Irreducible]].*

This means that the chain can be considered as a sample approximately distributed from $\pi$. 

The algorithm requires the choice of a conditional density $q$ called **proposal** or **candidate kernel**. The transition from $X^{(t)}$ to $X^{(t+1)}$ follows:
1. Generate $Y_{t}\sim q(y|x^{(t)})$.
2. Take
$$
X^{(t+1)}=
\begin{cases}
Y_{t} & \text{with probabiliity }\rho(x^{(t)},Y_{t}) \\
x^{(t)} & \text{with probabiliity }1-\rho(x^{(t)},Y_{t})
\end{cases}
$$
where
$$
\rho(x,y)=\min\left\{  \frac{\pi(y)}{\pi(x)} \frac{q(y,x)}{q(x,y)}, 1  \right\}
$$

If $q$ has wide enough support to reach any region of the state space $\mathcal{X}$ with positive mass under $\pi$, then the chain is irreducible with stationary density $\pi$. A sufficient condition would be $q$ is positive everywhere.

[[Markov Chain Monte Carlo (MCMC)]]