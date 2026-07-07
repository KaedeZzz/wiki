---
source: KaedeSync/_Knowledge/Physics/Mechanics/Vibrations/Orthogonality of Eigenvectors of EoM of Small Motion.md
ingested: 2026-07-06
---

The orthogonality condition is:
$$
\mathbf{u}^{(n)T}\mathbf{Mu}^{(m)}=0\text{ for }u\neq m
$$
###### Proof
Consider
$$
\begin{align}
\mathbf{Ku}^{(n)}=\omega_{n}^{2}\mathbf{Mu}^{(n)} \\
\mathbf{Ku}^{(m)}=\omega_{m}^{2}\mathbf{Mu}^{(m)}
\end{align}
$$
then:
$$
\begin{align}
\mathbf{u}^{(m)T}\mathbf{Ku}^{(n)}=\omega_{n}^{2}\mathbf{u}^{(m)T}\mathbf{Mu}^{(n)} \\
\mathbf{u}^{(n)T}\mathbf{Ku}^{(m)}=\omega_{m}^{2}\mathbf{u}^{(n)T}\mathbf{Mu}^{(m)}
\end{align}
$$
Transpose the second equation, noticing that $\mathbf{K}$ and $\mathbf{M}$ are symmetric:
$$
\begin{align}
\mathbf{u}^{(m)T}\mathbf{Ku}^{(n)}=\omega_{n}^{2}\mathbf{u}^{(m)T}\mathbf{Mu}^{(n)} \\
\mathbf{u}^{(m)T}\mathbf{Ku}^{(n)}=\omega_{m}^{2}\mathbf{u}^{(m)T}\mathbf{Mu}^{(n)}
\end{align}
$$
subtracting two equations:
$$
0=(\omega_{n}^{2}-\omega_{m}^{2})\mathbf{u}^{(m)T}\mathbf{Mu}^{(n)}
$$
Generally $\omega_{n}\neq\omega_{m}$ if $n\neq m$, so
$$
\mathbf{u}^{(m)T}\mathbf{Mu}^{(n)}=0\text{ if }n\neq m
$$

[[Eigenvalue Problem for Small Vibrations]]