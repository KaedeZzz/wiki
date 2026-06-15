---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Random Processes/Ergodic Random Processes.md"
ingested: 2026-06-09
---

Easy estimation methods for [[Ergodic]], [[Wide-Sense Stationary]] signals.

Mean ergodic signal:
$$
\begin{align}
\mu=\mathbb{E}[X_{n}]=\lim_{ N \to \infty } \frac{1}{N}\sum_{n=0}^{n-1}x_{n} \\
r_{XX}[k]=\lim_{ N \to \infty } \frac{1}{N}\sum_{n=0}^{n-1}x_{n}x_{n+k}
\end{align}
$$

These formula allow us to (assume ergodicity and) make estimations.

![[Mean Ergodicity Theorem]]