---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Random Processes/Markov Chain/Markov Chain.md"
ingested: 2026-06-09
---

[[Random Processes]]

Let $\{ X_{n} \}_{n\geq_{0}}$ be discrete random variables taking values in $S=\{ 1,\dots,L \}$

**Markov processes:**
A discrete time random process has the **Markov property** if
$$
f_{X_{t}|X_{t-1},\dots,X_{0}}(x_{t}|x_{t-1},\dots,x_{0})=f_{X_{t}|X_{t-1}}(x_{t}|x_{t-1})
$$
Such process is called a **Markov chain**.

![[Homogenous Markov Chain]]

We must also specify initial condition $\mathbf{p}^{(0)}$. Therefore we have:
$$
\mathbf{p}^{(n)}=\mathbf{p}^{(0)}Q
$$

The pair $(\mathbf{p}^{(0)}, Q)$ completely defines the Markov chain.