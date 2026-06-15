---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Linear Models/Auto-Regressive Process as GLM.md"
ingested: 2026-06-09
---

The [[Auto-Regressive (AR) Process]]
$$
X_{t}=\left( \sum_{i=1}^P a_{i}X_{t-i}\right)+W_{t}
$$
can be written as a [[General Linear Model (GLM)]]:
$$
\mathbf{x}=\mathbf{Ga}+\mathbf{e}
$$
where $\mathbf{e}$ is the vector of error values and
$$
\mathbf{G}=
\begin{bmatrix}
x_{-1} & x_{-2} & \dots & x_{-P} \\
x_{0} & x_{-1} & \dots & x_{-(P-1)} \\
\vdots & \vdots &  & \vdots \\
x_{N-2} & x_{N-3} & \dots & x_{N-P-1}
\end{bmatrix}
$$
Note that $\mathbf{G}$ has to contain values prior to time $n=0$ to calculate error terms $e_{n}$ at $n=0,1,\dots$
And also notice that $\mathbf{G}$ is made up of observed data.