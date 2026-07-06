---
source: KaedeSync/_Knowledge/Control Theory/State-Space Control/Kalman Filter/Kalman Filter.md
ingested: 2026-07-06
---

A **Kalman filter** is an algorithm that **estimates the state of a dynamic system** from a sequence of noisy measurements. It runs with two main steps:
1. Predict: use the model to estimate next state
2. Update: get a new observation and correct prediction with observation

Given equations 
$$
\begin{align}
\mathbf{x}_{t}=\mathbf{Ax}_{t-1}+\mathbf{v}_{t},\quad \mathbf{v}_{t}\sim \mathcal{N}(0, \Sigma_{v}) \\
\mathbf{y}_{t}=\mathbf{Bx}_{t}+\mathbf{w}_{t},\quad \mathbf{w}_{t}\sim \mathcal{N}(0,\mathbf{\Sigma}_{\mathbf{w}})
\end{align}
$$
the Kalman filter equations are given by:
$$
\begin{align}
\mu_{t|t-1} & =\mathbf{A}\mu_{t-1|t-1} \\
\mathbf{P}_{t|t-1} & =\mathbf{\Sigma}_{v}+\mathbf{AP}_{t-1|t-1}\mathbf{A}^{T} \\
\mathbf{K}_{t} & =\mathbf{P}_{t|t-1}\mathbf{B}^{T}(\mathbf{\Sigma}_{\mathbf{w}}+\mathbf{BP}_{t|t-1}\mathbf{B}^{T})^{-1} \\
\mu_{t|t} & =\mu_{t|t-1}+\mathbf{K}_{t}(\mathbf{y}_{t}-\mathbf{B}\mu_{t|t-1}) \\
\mathbf{P}_{t|t} & =(\mathbf{I}-K_{t}\mathbf{B})\mathbf{P}_{t|t-1}
\end{align}
$$