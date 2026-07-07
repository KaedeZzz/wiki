---
source: KaedeSync/_Knowledge/Physics/Mechanics/Vibrations/Receptance Function.md
ingested: 2026-07-06
---

$$
H_{q}(\omega)= \frac{\omega_{n}^{2}}{a_{n}} \frac{q_{k}}{F_{j}}= \frac{1}{1- \frac{\omega ^{2}}{\omega_{n}^{2}}+i 2\zeta_{n} \frac{\omega}{\omega_{n}}}
$$
where $a_{n}=u_{k}^{(n)}u_{j}^{(n)}$.

Log magnitude and phase:
$$
\begin{align}
20\log_{10}|H_{q}(\omega)| & =-20\log \sqrt{ \left( 1- \frac{\omega ^{2}}{\omega_{n}^{2}} \right)^{2}+4\zeta_{n}^{2} \frac{\omega ^{2}}{\omega_{n}^{2}} } \\
\phi_{q} & =-\tan^{-1} \frac{{2\zeta_{n} \frac{\omega}{\omega_{n}}}}{1- \frac{\omega ^{2}}{\omega_{n}^{2}}}
\end{align}

$$
$$
\begin{align}
\frac{\omega}{\omega_{n}}\to 0:\quad  & |H_{q}|_{dB}=0, \quad \phi_{q}=0 \\
\frac{\omega}{\omega_{n}}= 1:\quad  & |H_{q}|_{dB}=20\log \frac{1}{2\zeta_{n}}, \quad \phi_{q}= - \frac{\pi}{2} \\
\frac{\omega}{\omega_{n}}\to \infty:\quad  & |H_{q}|_{dB}=-40 \log \frac{\omega}{\omega_{n}}, \quad \phi_{q}=-\pi
\end{align}
$$

![[Pasted image 20241118134147.png]]