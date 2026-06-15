---
source: KaedeSync/_Knowledge/Machine Learning/Techniques/Logsumexp.md
ingested: 2026-06-08
---

[[Softmax Function]] causes overflow (too large) if the exponential is executed directly. Instead, we do:
$$
\begin{align}
\text{logsoftmax}(y_{k}) & =y_{k}-\text{logsumexp}(\mathbf{y}) \\
\text{logsumexp}(\mathbf{y}) & =\text{logsumexp}(\mathbf{y}-\max(\mathbf{y}))+\max(\mathbf{y})
\end{align}
$$
so that everything going into the $\exp$ function is negative, giving result $\leq1$ and no explosion happens.
