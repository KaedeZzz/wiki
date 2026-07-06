---
source: KaedeSync/_Knowledge/Control Theory/State-Space Control/Kalman Filter/Prediction Error Decomposition.md
ingested: 2026-07-06
---

Start with the Kalman prediction step:
$$
p(x_{t+1}|y_{1: t})=\mathcal{N}(x_{t+1}| \mu_{t+1|t}, P_{t+1|t})
$$
Observation model:
$$
y_{t+1}=Bx_{t+1}+w_{t+1}
$$
Conditional likelihood, using transformation of Gaussian variables:
$$
p(\mathbf{\mathbf{y}}_{t+1}|\mathbf{y}_{1: t})=\mathcal{N}(\mathbf{y}_{t+1}|\mathbf{B}\mu_{t+1|t},\mathbf{\Sigma}_{w}+\mathbf{BP}_{t+1|t}\mathbf{B}^{T})
$$
Using the probability chain rule, we obtain the full likelihood function:
$$
p(\mathbf{y}_{1: T})=p(y_{1})\prod_{t=1}^{T-1}p(y_{t+1}|y_{1: t})
$$
This incremental likelihood can be computed at each time step of the Kalman filter and accumulated over time to give the full likelihood.

*How can this be used for parameter estimation?*
We do ML/MAP estimates directly on the parameters:
$$
\begin{align}
\hat{\theta}_{ML} & =\arg\max_{\theta \in \Theta}p(y_{1:T}|\theta) \\
\hat{\theta}_{MAP} & =\arg\max_{\theta \in \Theta}p(y_{1:T}|\theta)p(\theta)
\end{align}
$$
[[Kalman Filter]]