---
source: KaedeSync/_Knowledge/Physics/Mechanics/Vibrations/Normal Coordinates and Decoupling of EoM of Small Motion.md
ingested: 2026-07-06
---

Define **normal** coordinates $\mathbf{y}$ by the transformation:
$$
\mathbf{q}=\mathbf{Uy}
$$
where $\mathbf{U}$ is the $(N\times N)$ matrix of **normalised eigenvectors**:
$$
\mathbf{U}=
\begin{bmatrix}
\mathbf{u}^{(1)} & \mathbf{u}^{(2)} & \dots & \mathbf{u}^{(N)}
\end{bmatrix}
$$
Then the [[Equation of Motion for Small Motion]] becomes:
$$
\mathbf{MU} \ddot{\mathbf{y}}+\mathbf{KUy}=\mathbf{Q}
$$
Left-multiply by $\mathbf{U}^{T}$ gives a set of $N$-coupled second order equations:
$$
\begin{align}
\mathbf{U}^{T}\mathbf{MU} \ddot{\mathbf{y}}+\mathbf{U}^{T}\mathbf{KUy}&=\mathbf{U}^{T}\mathbf{Q} \\
\text{consider orthogonality and normalisation:}\quad \mathbf{I} \ddot{\mathbf{y}}+[\text{diag}(\omega_{n}^{2})]\mathbf{y}&=\mathbf{U}^{T}\mathbf{Q}
\end{align}
$$
each row is a simple second order differential equation of the form
$$
\ddot{y_{j}}+\omega_{j}^{2}y_{j}=f_{j}
$$
where $f_{j}$ is the $j$-th row of $\mathbf{U}^{T}\mathbf{Q}$.

For free vibration, set $\mathbf{Q}=0$. Then the solution to each row becomes:
$$
y_{j}(t)=C_{j}\cos(\omega_{j}t-\phi_{j})
$$
Inserting coordinate transformation back gives:
$$
\mathbf{q}(t)=\sum_{j=1}^{N}C_{j}\mathbf{u}^{(j)}\cos(\omega_{j}t-\phi_{j})
$$
