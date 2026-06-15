---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Random Processes/Markov Chain/Gibb's Sampler.md"
ingested: 2026-06-09
---

Idea: design a Markov chain $q(\mathbf{x}'|\mathbf{x})$ that generates dependent samples $p(\mathbf{x})$.

Gibb's sampler assumes that the state space can be decomposed as
$$
\begin{align}
X & =X^{1}\times\dots \times X^{d} \\
\mathcal{X} &=\mathcal{X}^{1}\otimes \dots \otimes \mathcal{X}^{d} 
\end{align}
$$
that is, each $x \in X$ can be written as $x=(x^{1},\dots,x^{d})$ with $x^{i} \in X^{i}$. In addition, it assumes that the full conditional distributions of $\pi$ are possible to sample from.

For each component $i$ of $\mathbf{x}$ in turn, sample a new value from the conditional distribution of $x_{i}$ given all other variables:
$$
x_{i}'\sim p(x_{i}|x_{1},\dots,x_{i-1},x_{i+1},\dots,x_{D})
$$
where $D$ is the dimension.

[[Markov Chain Monte Carlo (MCMC)]]