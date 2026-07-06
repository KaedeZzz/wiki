---
source: KaedeSync/_Knowledge/Control Theory/State-Space Control/Kalman Filter/Kalman Gain.md
ingested: 2026-07-06
---

The  prediction equation of [[Kalman Filter]] expression can be arranged as:
$$
p(\mathbf{x}_{t}|\mathbf{y}_{1: t})=\mathcal{N}(\mu_{t|t},\mathbf{P}_{t|t})
$$
with parameters given by
$$
\mu_{t|t}=\mu_{t|t-1}+K_{t}(\mathbf{y}_{t}-\mathbf{B}\mu_{t|t-1})\quad \text{and}\quad \mathbf{P}_{t|t}=(\mathbf{I}-K_{t}\mathbf{B})\mathbf{P}_{t|t-1}$$
where
$$
K_{t}=\mathbf{P}_{t|t-1}\mathbf{B}^{T}(\mathbf{\Sigma}_{\mathbf{w}}+\mathbf{BP}_{t|t-1}\mathbf{B}^{T})^{-1}
$$
is known as the Kalman gain.

The Kalman gain answers:
- "*Given a mismatch in measurement space, how much and in what direction should I move the state estimate in state space?*"

