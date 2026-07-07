---
source: KaedeSync/_Knowledge/Physics/Mechanics/Newton's Second Law of Angular Momentum.md
ingested: 2026-07-06
---

![[Torque]]

![[Angular Momentum 1]]

Differentiate the angular momentum with respect to time:
$$
\begin{align}
\dot{\mathbf{h}}_{P} & =\sum_{i}(\dot{\mathbf{r}}_{i}-\dot{\mathbf{r}}_{P})\times m_{i}\dot{\mathbf{r}}_{i}+\sum_{i}(\mathbf{r}_{i}-\mathbf{r}_{P})\times m_{i} \ddot{\mathbf{r}}_{i} \\
 & =-\dot{\mathbf{r}}_{P}\times \sum_{i}m_{i}\dot{\mathbf{r}}_{i}+\mathbf{Q}^{(e)}_{P}
\end{align}

$$
therefore,
$$
\mathbf{Q}^{(e)}_{P}=\dot{\mathbf{h}}_{P}+\dot{\mathbf{r}}_{P}\times \mathbf{p}
$$
where $\mathbf{p}$ is the linear momentum of the rigid body.

In other words, the torque equals the rate of change of angular momentum **plus** *the correction term if the point $P$ moves.*

If $P$ is the centre of mass $G$, then $\mathbf{Q}^{(e)}_{G}=\dot{\mathbf{h}}_{G}$ for that $\dot{\mathbf{r}}_{G}\parallel \mathbf{p}$. If $P$ is a fixed point, then $\mathbf{Q}_{P}^{(e)}=\dot{\mathbf{h}}_{P}$ for that $\dot{\mathbf{r}}_{P}=\mathbf{0}$.

[[Mechanics and Dynamics]], [[Newton's Second Law for Rigid Body]]