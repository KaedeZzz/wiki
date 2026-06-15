---
source: KaedeSync/_Knowledge/Machine Learning/Basics/Concepts/Stochastic Gradient Descent.md
ingested: 2026-06-08
---

Idea: add noise.

Computes gradient based on a set, not all, of points: a mini-batch.

$$
g=\sum_{i \in \mathcal{B}_{t}} \frac{{\partial L}}{\partial \theta}
$$

It can escape local minima, and is computationally less expensive.
It does not converge in traditional sense, so one approach is to arrange a [[Learning Rate]] schedule, that is, to decrease learning rate along training.

[[Gradient Descent]]