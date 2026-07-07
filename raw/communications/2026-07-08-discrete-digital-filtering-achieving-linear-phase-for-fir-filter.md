---
source: KaedeSync/_Knowledge/Communications/Discrete/Digital Filtering/Achieving Linear Phase for FIR Filter.md
ingested: 2026-07-08
---

[[FIR Design of Lowpass Filter]]

Linear phase $G(e^{j\theta})=|G(e^{j\theta})|e^{-j\theta N/2}$ is achieved if $g_{k}=g_{N-k}$.
$$
\begin{align}
G(e^{j\theta}) & =\sum_{k=0}^{N}g_{k}e^{-j\theta k} \\
 & =e^{-j\theta N/2}(g_{0}e^{j\theta N/2}+g_{N}e^{-j\theta N/2}+g_{1}e^{j\theta (N/2-1)}+g_{N-1}e^{-j\theta (N/2-1)}+\dots) \\
 & =e^{-j\theta N/2}\underbrace{\left( 2g_{0}\cos\left( \theta\frac{ N}{2} \right)+2g_{1}\cos\left( \theta\ \frac{{N-1}}{2} \right) +\dots\right)}_{|G(e^{j\theta})|}
\end{align}
$$
