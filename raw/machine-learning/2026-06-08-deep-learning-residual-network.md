---
source: KaedeSync/_Knowledge/Machine Learning/Deep Learning/Residual Network.md
ingested: 2026-06-08
---

Traditional networks:
$$
\begin{align}
h_{1} & =f_{1}(x,\theta_{1}) \\
h_{2} & =f_{2}(h_{1},\theta_{2}) \\
y & =h_{3}(h_{2},\theta_{3})
\end{align}
$$
Residual networks: *always pass $x$*
$$
\begin{align}
h_{1} & =x+f_{1}(x,\theta_{1}) \\
h_{2} & =h_{1}+f_{2}(h_{1},\theta_{2}) \\
y & =h_{2}+f_{3}(h_{2},\theta_{3})
\end{align}
$$
idea: even if $f'$ vanishes, the gradients will back propagate to $x$.

[[Deep Learning]]