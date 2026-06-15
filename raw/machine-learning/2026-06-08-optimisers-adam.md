---
source: KaedeSync/_Knowledge/Machine Learning/Optimisers/ADAM.md
ingested: 2026-06-08
---

Full name: Adaptive Moment Estimation.

![[Normalised Gradient Descent]]

ADAM computes mean and point-wise squared gradients with momentum:
$$
\begin{align}
\mathbf{m}_{t+1} & =\beta \mathbf{m}_{t}+(1-\beta) \frac{{\partial L(\theta_{t})}}{\partial \theta} \\
\mathbf{v}_{t+1} & =\gamma \mathbf{v}_{t}+(1-\gamma) \left( \frac{{\partial L(\theta_{t})}}{\partial \theta} \right)^{2} \\
\end{align}
$$
then, we moderate the gradients near start of the sequence:
$$
\begin{align}
\tilde{\mathbf{m}}_{t+1} & = \frac{\mathbf{m}_{t+1}}{1-\beta^{t+1}} \\
\tilde{\mathbf{v}}_{t+1} & = \frac{\mathbf{v}_{t+1}}{1-\gamma^{t+1}}
\end{align}
$$
finally update the parameters
$$
\theta_{t+1}=\theta_{t}-\alpha  \frac{\tilde{\mathbf{m}}_{t+1}}{\sqrt{ \tilde{\mathbf{v}}_{t+1} }+\epsilon}
$$
