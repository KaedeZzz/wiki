---
source: KaedeSync/_Knowledge/Control Theory/Stability/Nyquist/Asymptote on Nyquist Diagram.md
ingested: 2026-07-06
---

If there exists an open-loop pole of magnitude $1$ on the unit circle, then the [[Nyquist Diagram]] will be asymptotic to a straight line as it tends to infinity. 

###### Example
Suppose that $G(z)$ has a pole at $1$, i.e.
$$
G(z)=\frac{1}{z-1}F(z)
$$
where $F(z)$ has no poles or zeros at $z=1$.
Then for $z\approx 1$, Taylor expansion of $F(z)$ gives
$$
\begin{align}
G(z)&=\frac{1}{z-1}\left[ F(1)+F'(1)(z-1)+\frac{F''(1)}{2}(z-1)^{2}+\dots \right] \\
&\approx\frac{F(1)}{z-1}+F'(1)\text{ (ignore higher order terms at }z\to 1\text{)} \\
 G(e^{j\theta})& \approx \frac{F(1)}{e^{j\theta}-1}+F'(1)
\end{align}
$$

Consider that:
$$
\begin{align}
\frac{1}{e^{j\theta}-1}&=\{ e^{j\theta/2}(e^{j\theta/2}-e^{-j\theta/2}) \}^{-1} \\
&=\frac{e^{-j\theta/2}}{2j\sin\left( \frac{\theta}{2} \right)} \\
&=-\frac{1}{2}-\frac{j}{2\tan\left( \frac{\theta}{2} \right)}
\end{align}
$$
Thus:
$$
G(e^{j\theta})\approx - \frac{1}{2}F(1)+F'(1)-j \frac{F(1)}{2\tan\left( \frac{\theta}{2} \right)}
$$
Therefore, the asymptote as $\theta\to 0$ is a straight line with constant real part evaluating to $- \frac{1}{2}F(1)+F'(1)$.
