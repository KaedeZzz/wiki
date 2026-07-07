---
source: KaedeSync/_Knowledge/Computer Vision/Camera/Projective Camera.md
ingested: 2026-07-06
---

We would also consider another camera model, the projective camera, which is described by the general $3\times 4$ matrix $P$:
$$
\tilde{\mathbf{w}}=\mathbf{P}\tilde{\mathbf{X}}\quad \text{where}\quad \mathbf{P}=
\begin{bmatrix}
p_{11} &  p_{12} & p_{13} & p_{14} \\
P_{21} & p_{22} & p_{23} & p_{24} \\
p_{31} & p_{32} & p_{33} & p_{34}
\end{bmatrix}
$$
The projective camera has $11$ degrees of freedom (since the overall scale of $P$ does not matter).

Since [[The Perspective Camera]] is a special case of the projective camera, any results we derive for the projective camera will also hold for the perspective camera.
