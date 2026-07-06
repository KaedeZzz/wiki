---
source: KaedeSync/_Knowledge/Control Theory/PID/Proportional-Integral-Derivative Controller (PID).md
ingested: 2026-07-06
---

[[Control]]

A proportional–integral–derivative controller (PID controller) is a control loop feedback mechanism (controller) commonly used in industrial control systems. 

![[Pasted image 20241105221327.png]]

The control variable $u(t)$ is given by a weighted sum:
$$
u(t)=K_{p}e(t)+K_{i}\int_{0}^{t}e(t)+K_{d} \frac{de(t)}{dt}
$$
where $e(t)=r(t)-y(t)$ is the error term.

The [[Transfer Function]] in the Laplace domain ([[Laplace Transform]]) is:
$$
L(s)=K_{p}+\frac{K_{i}}{s}+K_{d}s
$$
where $s$ is the complex frequency.

Proportional gain $K_{p}$:
- too high: unstable / oscillatory
- too low: irresponsive

Integral gain $K_{i}$:
- can eliminate steady-state gain
- too high: overshoot

Derivative gain $K_{d}$:
- predicts system behaviour
- very sensitive to noise, usually given low-pass filter