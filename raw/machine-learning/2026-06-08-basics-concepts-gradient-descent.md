---
source: KaedeSync/_Knowledge/Machine Learning/Basics/Concepts/Gradient Descent.md
ingested: 2026-06-08
---

We need to minimise loss on the training data:
$$
\mathcal{L}(\theta,\{ \hat{x}_{i},\hat{y}_{i} \}_{i=1}^{n})=\sum_{i=1}^{n}L(f(\hat{x}_{i},\theta),\hat{y}_{i})
$$
algorithm:
1. Initialize $\theta^{(0)}=something.$
2. For each loop, compute the gradient
$$
g=\frac{{\partial L}}{\partial \theta}(\theta^{(i)};\mathcal{D})
$$
3. update parameters:
$$
\theta^{(i+1)}=\theta^{(i)}-\alpha g
$$
where $\alpha$ is the [[Learning Rate]].
4. Repeat until (recognised as) convergence.

[[Machine Learning]]