---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Random Processes/Markov Chain/Homogenous Markov Chain.md"
ingested: 2026-06-09
---

A homogenous markov chain is one where
$$
f_{X_{t}|X_{t-1}}(x|y)=f_{X_{1}|X_{0}}(x|y)
$$

If $X_{t}$ are discrete, we can define the **transition matrix** $Q$ on a discrete space:
$$
[Q]_{ij}=P(X_{t+1}=j|X_{t}=i)
$$

$Q$ is a discrete distribution in $j$, so $\sum_{j}Q_{ij}=1$
