---
source: KaedeSync/_Knowledge/Communications/Filter Design/Uncorrelated Signal Filter.md
ingested: 2026-07-08
---

Where signal and noise have $0$ correlation for all time difference. 
Consider

![[Wiener-Hopf Equations]]

If $x_{n}=d_{n}+v_{n}$ and $\mathbb{E}[d_{n}v_{n+q}]=0\quad\text{for all }q$ :
-  $r_{xd}[q]=r_{dd}[q]$
- $r_{x x}[q]=r_{dd}[q]+r_{vv}[q]$
- Therefore:

$$
\begin{align}
S_{x}(e^{j\Omega}) & =S_{d}(e^{j\Omega})+S_{v}(e^{j\Omega}) \\
H(e^{j\Omega}) & =\frac{S_{d}(e^{j\Omega})}{S_{d}(e^{j\Omega})+S_{v}(e^{j\Omega})}=\frac{1}{1+1 / \rho(\Omega)}
\end{align}
$$
where $\rho(\Omega)$ is the [[Signal-to-Noise Ratio (SNR)]].
