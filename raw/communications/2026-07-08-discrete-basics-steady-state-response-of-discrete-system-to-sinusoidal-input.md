---
source: KaedeSync/_Knowledge/Communications/Discrete/Basics/Steady-state Response of Discrete System to Sinusoidal Input.md
ingested: 2026-07-08
---

[[Control]]
$$
\tilde{y}_{k}=G(e^{j\theta})e^{j\theta k}=|G(e^{j\theta})|e^{j(\theta k+\angle G(e^{j\theta}))}
$$
###### Derivation
Assume input being $x_{k}=e^{j\theta k}$, so $X(z)=\frac{1}{1-e^{j\theta}z^{-1}}$.
Assume
$$
G(z)=\frac{{b(z^{-1})}}{(1-p_{1}z^{-1})\dots(1-p_{n}z^{-1})}
$$
where $b(z^{-1})$ indicates a polynomial of $z^{-1}$.

Multiply $G$ by $X$:
$$
\begin{align}
G(z)X(z)&=\frac{b(z^{-1})}{(1-p_{1}z^{-1})\dots(1-p_{n}z^{-1})\underbrace{(1-e^{j\theta}z^{-1})}_{X(z)}} \\
\text{partial fraction}\to&=\underbrace{\sum_{i} \frac{\alpha_{i}}{1-p_{i}z^{-1}}}_{\text{transient response}}+\underbrace{ \frac{\beta}{1-e^{j\theta}z^{-1}}}_{\text{steady-state response}}
\end{align}
$$
Multiply each side by $\frac{1}{X(z)}=1-e^{j\theta}z^{-1}$:
$$
\begin{align}
G(z)=\frac{G(z)X(z)}{X(z)}&=\beta+(1-e^{j\theta}z^{-1})\sum_{i} \frac{\alpha_{i}}{1-p_{i}z^{-1}} \\
G(e^{j\theta})&=\beta
\end{align}
$$

Therefore,
$$
\begin{align}
\tilde{Y}(z)&=\frac{\beta}{1-e^{j\theta}z^{-1}}=\frac{G(e^{j\theta})}{1-e^{j\theta}z^{-1}} \\
y_{k}&=G(e^{j\theta})e^{j\theta k}
\end{align}
$$

Steady-state response to a real sinusoidal input:
$$
x_{k}=\cos(\theta k)=\frac{1}{2}(e^{j\theta k}+e^{-j\theta k})
$$
$$
\begin{align}
y_{k} & =\frac{G(e^{j\theta})}{2}(e^{j\theta k}+e^{-j\theta k}) \\
 & =|G(j\theta)|\cos(\theta k+\angle G(j\theta))
\end{align}
$$
