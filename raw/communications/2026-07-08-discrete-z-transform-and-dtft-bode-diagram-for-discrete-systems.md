---
source: KaedeSync/_Knowledge/Communications/Discrete/z-Transform and DTFT/Bode Diagram for Discrete Systems.md
ingested: 2026-07-08
---

[[z-Transform]]

![[Bode Diagram]]

![[Pasted image 20241028235454.png]]

For discrete Bode diagram:
$$
\tilde{y}_{k}=|G(j\theta)|\cos(\theta k+\angle G(j\theta))
$$
We plot magnitude and phase of output sinusoid with respect to $\theta$.

Note that:
- Values of $\theta$ above $2\pi$ are redundant; $e^{j\theta}=e^{j(\theta+2\pi)}$.
- Negative frequencies mirror positive frequencies for real-valued signals, hence Bode diagram is generally limited to the frequency interval $[0,\pi)$.

###### Expression

A way to represent transfer function with [[Poles]] and zeros:
$$
G(z)=c\frac{\prod_{k=1}^{m}(z-z_{k})}{\prod_{k=1}^{m}(z-p_{k})}
$$
where $z_{k}$ and $p_{k}$ are all poles and zeros.
Therefore, we can derive expression for magnitude and phase:
- Magnitude
$$
\begin{align}
|G(e^{j\theta})|_{dB}&=20\log|G(e^{j\theta})| \\
&=20\left(\log|c|+\sum_{k=1}^{m}\log|e^{j\theta}-z_{k}|-\sum_{k=1}^{m}\log|e^{j\theta}-p_{k}|\right)
\end{align}
$$
- Phase
$$
\angle G(e^{j\theta})=\angle(c)+\sum_{k=1}^{m}\angle (e^{j\theta}-z_{k})-\sum_{k=1}^{m}\angle (e^{j\theta}-p_{k})
$$
"sum of rotated angles w.r.t. poles and zeros"

![[Pasted image 20241222171856.png]]
###### Properties

- The magnitude is given by the product of the distances from the zeros to $e^{j\theta}$ divided by the product of the distances from the poles to $e^{j\theta}$. In dB scale, products and divisions become sums and subtractions.
- Thus, when $e^{j\theta}$ is close to a pole, the magnitude rises; when $e^{j\theta}$ is close to a zero, the magnitude falls.
- The phase is given by the sum of the angles from the zeros to $e^{j\theta}$ minus the sum of the angles from the poles to $e^{j\theta}$.
- Thus, when $e^{j\theta}$ goes across a zero or a pole. the phase flips a $\pi$.
- Unlike continuous cases, there is no simple rules for drawing Bode diagrams of digital systems. Use numerical tools!