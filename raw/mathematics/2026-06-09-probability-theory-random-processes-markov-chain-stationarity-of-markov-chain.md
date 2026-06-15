---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Random Processes/Markov Chain/Stationarity of Markov Chain.md"
ingested: 2026-06-09
---

[[Markov Chain]]
Consider transition probability matrix $Q$ with state-space $S$. The pmf $\pi$ is **invariant** for $Q$ if for all $j\in S$,
$$
\sum_{i\in S}\pi_{i}Q_{i,j}=\pi_{j}\text{ or (vectorized) }\pi Q=\pi
$$
That is, $\pi$ being [[Left Eigenvector]] of $Q$
In this way $(\pi,Q)$ is [[Strictly Stationary]].