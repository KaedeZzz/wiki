---
source: KaedeSync/_Knowledge/Machine Learning/Basics/Theories/Gradient Momentum.md
ingested: 2026-06-08
---

We define momentum as:
$$
\mathbf{m}_{t+1}=\beta \cdot \mathbf{m}_{t}+(1-\beta)\sum_{i \in \mathcal{B}_{t}} \frac{{\partial L}}{\partial \theta}
$$
and do [[Gradient Descent]] as:
$$
\theta_{t+1}=\theta_{t}-\alpha \cdot \mathbf{m}_{t+1}
$$
This adds a vecocity-like memory term so updates keep moving in a consistent direction instead of reacting only to the current gradient.