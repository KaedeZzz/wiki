---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Random Processes/Linear Systems/Linear Systems and Random Processes.md"
ingested: 2026-06-09
---

For an [[Linear Time-Invariant (LTI)]]:
$$
y_{n}=\sum_{k=-\infty}^{\infty}h_{k}x_{n-k}=x_{n}*h_{n}
$$
output correlation functions and power spectra can be expressed as:
$$
\begin{align}
r_{XY}(k) & =\mathbb{E}[X_{n}Y_{n+k}]=\sum_{l=-\infty}^{\infty}h_{l}r_{XX}(k-l)=h_{k}*r_{XX}(k) \\
r_{YY}(l) & =\mathbb{E}[Y_{n}Y_{n+k}]=\sum_{k=-\infty}^{\infty}\sum_{i=-\infty}^{\infty}h_{k}h_{i}r_{XX}[l+i-k] \\
 & =h_{l}*h_{-l}*r_{XX}(l)
\end{align}

$$

Power spectrum:
$$
S_{Y}(e^{j\omega T})=|H(e^{j\omega T})|^{2}S_{X}(e^{j\omega T})
$$

[[Random Processes]]