---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Random Processes/Markov Chain/Markov Transition Kernel.md"
ingested: 2026-06-09
---

A Markov transition kernel on a measurable space $(X,\mathcal{X})$ is a function $\mathcal{P}:X\times \mathcal{X}\to[0,1]$ such that:
$$
\begin{align}
 & \mathcal{P}(x,\cdot) \text{ is a probability measure for all } x \in X \\
 & \mathcal{P}(\cdot, A) \text{ is measurable for all }A \in \mathcal{X}
\end{align}
$$
The first condition tells that for a Markov chain,
$$
P(X_{n+1} \in A|X_{n}=x)=\mathcal{P}(x,A)
$$
