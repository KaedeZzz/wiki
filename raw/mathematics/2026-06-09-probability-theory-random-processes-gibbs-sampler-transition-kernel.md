---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Random Processes/Gibb's Sampler Transition Kernel.md"
ingested: 2026-06-09
---

A single coordinate [[Markov Transition Kernel]] in the [[Gibb's Sampler]] can be written as:
$$
\begin{align}
\mathcal{P}_{i}(x,A) & =\pi(X^{i} \in A_{x^{-i}}|X^{-i}=x^{-i}) \\
A_{x^{-i}} & =\{ y \in X^{i}:(x^1,\dots,x^{i-1},y,x^{i+1},\dots,x^{d}) \in A \}
\end{align}
$$
where $x^{-i}$ denotes exclusion of the $i$-th component, and $A_{x^{-i}}$ represents all points in $A$ which can be obtained from changing the $i$-th component of $x$.
