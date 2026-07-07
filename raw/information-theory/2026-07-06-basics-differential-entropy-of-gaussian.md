---
source: KaedeSync/_Knowledge/Information Theory/Basics/Differential Entropy of Gaussian.md
ingested: 2026-07-06
---

[[Differential Entropy]] of [[Gaussian Distribution]]:

Let $X\sim N(\mu,\sigma ^{2})$. The pdf $\phi$ is given by
$$
\phi(x)= \frac{1}{\sqrt{ 2\pi \sigma ^{2} }}\exp\left\{  -\frac{(x-\mu)^{2}}{2\sigma ^{2}} \right\}
$$

The differential entropy is then
$$
\begin{align}
h(X) & = \int \phi(x)\log \frac{1}{\phi(x)}dx \\
 & =-\int \phi(x) \frac{\ln\phi(x)}{\ln 2} dx \\
 & =-\frac{1}{\ln 2}\int \phi(x)\left[ - \frac{(x-\mu)^{2}}{2\sigma ^{2}}-\ln \sqrt{ 2\pi\sigma ^{2} } \right] \\
 & =\frac{1}{\ln 2}\left[ \frac{Var(X)}{2\sigma ^{2}}+\frac{1}{2}\ln 2\pi\sigma ^{2} \right] \\
 & =\frac{1}{\ln{2}}\left[ \frac{1}{2}+\frac{1}{2}\ln 2\pi\sigma ^{2} \right] \\
 & = \frac{1}{\ln 2}\left[ \frac{1}{2}\ln 2\pi e\sigma ^{2} \right]=\frac{1}{2}\log 2\pi e\sigma ^{2}
\end{align}
$$
