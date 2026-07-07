---
source: KaedeSync/_Knowledge/Physics/Mechanics/Vibrations/Response Formula of Vibration.md
ingested: 2026-07-06
---

Assume the input to the system is sinusoidal such that $\mathbf{Q}=\bar{\mathbf{Q}}e^{i\omega t}$. The response is then $\mathbf{q}=\bar{\mathbf{q}}e^{i\omega t}$.
$$
-\omega ^{2}\mathbf{M}\bar{\mathbf{q}}e^{i\omega t}+\mathbf{K}\bar{\mathbf{q}}e^{i\omega t}=\bar{\mathbf{Q}}e^{i\omega t}
$$
Decoupling gives:
$$
\begin{align}
-\omega ^{2}\mathbf{I}\bar{\mathbf{y}}e^{i\omega t}+[\text{diag}(\omega_{n} ^{2})]\bar{\mathbf{y}}e^{i\omega t}&=\mathbf{U}^{T}\bar{\mathbf{Q}}e^{i\omega t} \\
[\text{diag}(\omega_{n}^{2}-\omega ^{2})]\bar{\mathbf{y}}&=\mathbf{U}^{T}\bar{\mathbf{Q}} \\
\bar{\mathbf{y}}&=\left[ \frac{1}{\text{diag}(\omega_{n}^{2}-\omega ^{2})}  \right]\mathbf{U}^{T}\bar{\mathbf{Q}} \\
\bar{\mathbf{q}}&=\mathbf{U}\left[ \frac{1}{\text{diag}(\omega_{n}^{2}-\omega ^{2})}  \right]\mathbf{U}^{T}\bar{\mathbf{Q}} \\
\end{align}
$$
Now suppose the sinusoidal forcing is applied to the $j$-th coordinate only:
$$
\mathbf{Q}=
\begin{bmatrix}
0 \\
\vdots \\
F \\
\vdots \\
0
\end{bmatrix}
e^{i\omega t}
$$
Then:
$$
H_{jk}= \frac{q_{k}}{F_{j}}=\sum_{n=1}^{N} \frac{{u_{k}^{(n)}u_{j}^{(n)}}}{\omega_{n}^{2}-\omega ^{2}}
$$
where $j$ is the excitation point and $k$ is the measurement point.

![[Transfer Function of Vibration]]

![[Bode Diagram of Response Formula of Vibration 1]]

[[Normal Coordinates and Decoupling of EoM of Small Motion]]