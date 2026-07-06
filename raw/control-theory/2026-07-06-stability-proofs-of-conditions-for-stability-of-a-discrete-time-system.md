---
source: KaedeSync/_Knowledge/Control Theory/Stability/Proofs of Conditions for Stability of a Discrete-time System.md
ingested: 2026-07-06
---

#ESSENTIAL 
[[BIBO Stability]]
###### Proof 1: $G$ is stable $\implies$ all poles have $\lvert p_{i} \rvert<1$
Equivalent argument:  $\exists \ p$ such that $\lvert p \rvert\geq 1\implies$ $G$ unstable

*Suppose* all [[Poles]] are distinct. Then $G$ can be decomposed into
$$
G(z)=\frac{\alpha_{1}}{1-p_{1}z^{-1}}+\frac{\alpha_2}{1-p_{2}z^{-1}}+\dots+\frac{\alpha_{n}}{1-p_{n}z^{-1}}
$$
Then:
$$
g_{k}=\alpha_{1}p_{1}^{k}+\alpha_{2}p_{2}^{k}+\dots+\alpha_{n}p_{n}^{k}
$$

Suppose all $|p|<1$, then output is unbounded, $G$ is *unstable*.

Suppose some $|p|=1$, let us denote:
$$
G(z)=\frac{\alpha_{i}}{1-e^{j\theta}z^{-1}}+\tilde{G}(z)
$$
(note that $g_{k}=\alpha_{i}e^{j\theta k}+\alpha_{1}p_{1}^{k}+\dots+\alpha_{i-1}p_{i-1}^{k}+\alpha_{i+1}p_{i+1}^{k}+\dots+\alpha_{n}p_{n}^{k}$.)
Consider the input
$$
U(z)=\frac{\alpha_{i}z^{-1}}{1-e^{j\theta}z^{-1}}
$$
The input is a time lag of $\alpha_{i}e^{j\theta k}$ by 1 timestep so it is bounded.
The output:
$$
Y(z)=G(z)U(z)=\frac{\alpha_{i}^{2}z^{-1}}{(1-e^{j\theta}z^{-1})^{2}}+\tilde{G}(z)U(z)
$$
The first term corresponds to the sequence
$$
y_{k}'=k\alpha_{i}^{2}e^{j\theta(k-1)}
$$
whose magnitude grows linearly with $k$ and thus is not bounded. Thus $G$ is *unstable*.

Suppose there are repeated poles: similar.

###### Proof 2: $\sum_{k=0}^{\infty}\lvert g_{k} \rvert<\infty\implies G$ is stable

Let $\{ u_{k} \}$ be arbitrary bounded input. That is, $|u_{k}|<M$ for some $M>0$. The output is given by [[Discrete Convolution]]:
$$
y_{k}=\sum_{i=0}^{k}g_{i}u_{k-i}
$$
Thus,
$$
\begin{align}
|y_{k}|&=\left\lvert  \sum_{i=0}^{k}g_{i}u_{k-i}  \right\rvert  \\
&\leq\sum_{i=0}^{k}|g_{i}||u_{k-i}| \\
&<M\sum_{i=0}^{k}|g_{i}| \\
&<M\sum_{i=0}^{\infty}|g_{i}|<\infty
\end{align}
$$
therefore $\{ y_{k} \}$ is bounded by $M\sum_{k=0}^{\infty}|g_{k}|$.

###### Proof 3: All poles have $|p_{i}|<1\implies \sum_{k=0}^{\infty}|g_{k}|<\infty$
(from example papers)

The transfer function $G(z)$ can be expressed as the following form:

![[General Form of z-Transfer Function]]

which can be decomposed into:
$$
\sum_{i=1}^{r}\frac{\sum_{j=0}^{n_{i-1}}B_{ij}z^{-j}}{(1-p_{i}z^{-1})^{n_{i}}}
$$
Recall [[Partial Fraction]] knowledge from IB, this can be further decomposed into:
$$
\sum_{i=1}^{r}\sum_{l=1}^{n_{r}} \frac{A_{ij}}{(1-p_{i}z^{-1})^{l}}
$$
Then:
$$
\begin{align}
g_{k}&=\sum_{i=1}^{r}\sum_{l=1}^{n_{r}}A_{ij}\cdot\mathcal   Z^{-1} \left\{ \frac{1}{(1-p_{i}z^{-1})^{l}} \right\} \\
&=\sum_{i=1}^{r}\sum_{l=1}^{n_{r}}A_{ij} \frac{(k+l-1)!}{k!(l-1)!} p_{i}^{k}
\end{align}
$$
now, summation:
$$
\begin{align}
\sum_{i=0}^{\infty}|g_{k}|&=\sum_{i=1}^{r}\sum_{l=1}^{n_{r}}|A_{ij}|\sum_{k=0}^{\infty} \frac{(k+l-1)!}{k!(l-1)!} (p_{i}^{-1})^{-k} \\
&=\sum_{i=1}^{r}\sum_{l=1}^{n_{r}}|A_{ij}|\mathcal G(p_{i}^{-1})\text{ where $\mathcal G(z)=\mathcal Z\{ \frac{(k+l-1)!}{k!(l-1)!} \}$}\\
\end{align}
$$
From databook, $\mathcal G(z)=\frac{1}{(1-z^{-1})^{l}}$, so
$$
\sum_{i=0}^{\infty}|g_{k}|=\sum_{i=1}^{r}\sum_{l=1}^{n_{r}}|A_{ij}| \frac{1}{(1-p)^{l}}
$$
which is a finite sum $< \infty$.

###### Proof 4: $\sum_{k=0}^{\infty}|g_{k}|=\infty\implies$ *ANY* finite bound can be exceeded by output from bounded input $\implies G$ is unstable

From definition, let $y_{k}=\sum_{i=0}^{k}g_{i}u_{k-i}$.
Let $u_{k-i}= 1\text{ if }g_{i}\geq 0 \text{ else } -1\text{ if }g_{i}< 0$ for $0\leq i\leq k$; therefore $y_{k}=\sum_{i=0}^{k}|g_{i}|$.

Since $\sum_{k=0}^{\infty}|g_{k}|=\infty$, from definition of a series summing into infinity, this indicates:
*For any arbitrary $N>0$, there exists (large enough) $k>0$ such that $\sum_{i=0}^{k}|g_{i}|>N$.* 

This means no finite boundary $N$ can bound the output as $k$ tends to infinity.
Therefore, $G$ is unstable.

