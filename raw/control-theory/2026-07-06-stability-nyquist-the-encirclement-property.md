---
source: KaedeSync/_Knowledge/Control Theory/Stability/Nyquist/The Encirclement Property.md
ingested: 2026-07-06
---

[[Nyquist Stability Criterion]]

For any rational function $F(z)$, the **number of encirclements of the origin** by *Nyquist trajectory* $F(e^{j\theta})$ tells something about poles and zeros:

Consider a fact: for a point on complex plane $z$, as $\theta$ goes from $0$ to $2\pi$,
- if $z$ is within (*or on*) unit circle, increase in $\angle (e^{j\theta}-z)$ is $2\pi$ (the vector $e^{j\theta}-z$ goes $180^{\circ}$ around point $z$)
- if$z$ is outside the unit circle, increase in $\angle(e^{j\theta}-z)=0$ (the vector oscillates and go back eventually)

And, for rational function
$$
F(z)=A \frac{{(z-z_{1})(z-z_{2})\dots(z-z_{m})}}{(z-p_{1})(z-p_{2})\dots(z-p_{n})}
$$
we have:
$$
\angle F(e^{j\theta})=\angle A +\sum_{i=1}^{m}\angle(e^{j\theta}-z_{i})-\sum_{j=1}^{n}(e^{j\theta}-z_{j})
$$
Let:
- $N_{z,i}$ denotes the number of zeros inside unit circle
- $N_{p,i}$ denotes the number of poles inside unit circle

therefore, the overall increase $\alpha$ of $\angle F(e^{j\theta})$ satisfies:
$$
\alpha=2\pi(N_{z,i}-N_{p,i})
$$
hence the number of encirclements of the origin:
$$
\mathcal C=N_{z,i}-N_{p,i}
$$