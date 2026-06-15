---
source: KaedeSync/_Knowledge/Machine Learning/Optimisers/Nesterov Accelerated Momentum.md
ingested: 2026-06-08
---

[[Gradient Momentum]] acts as a prediction of the position of next step.

$$
\begin{align}
\mathbf{m}_{t+1} & =\beta \cdot \mathbf{m}_{t}+(1-\beta)\sum_{i \in \mathcal{B}_{t}} \frac{{\partial L(\theta_{t}-\alpha \mathbf{m}_{t})}}{\partial \theta} \\
\theta_{t+1} & =\theta_{t}-\alpha \mathbf{m}_{t+1}
\end{align}
$$