---
source: KaedeSync/_Knowledge/Machine Learning/Deep Learning/Physics Informed Neural Network (PINN).md
ingested: 2026-06-08
---

Instead of discretizing the [[Partial Differential Equation (PDE)]] and solving at grid points, PINN represent the unknown solution directly with a neural network.

**PDE Setup**
A generic time-dependent nonlinear PDE in the form
$$
\partial_t u(x,t) + Q[u](x,t) = 0, \qquad x \in \Omega,\ t \in [0,T]
$$
with initial and boundary conditions of the form
$$
u(x,0)=g(x), \qquad \mathcal{B}[u(x,t)]=0 \ \text{ on } \partial\Omega\times[0,T]
$$
where $Q[\cdot]$ is a linear or nonlinear differential operator, $\Omega$ is the spatial domain, and $\mathcal{B}$ is the boundary operator.

**PINN for Forward Problems**
PINNs represent the unknown solution directly with a neural network. Then the network is forced to satisfy:
- the initial condition,
- the boundary condition,
- the PDE residual inside the domain.

Four steps:
- represent the unknown solution
$$
u(x,t)\approx u_{\theta}(x,t)
$$
- insert into PDE and define the PDE residual
$$
R_{\theta}(x,t)=\partial_{t}u_{\theta}(x,t)+Q[u_{\theta}](x,t)
$$
- minimize a composite loss of the form
$$
L(\theta)=L_{ic}(\theta)+L_{bc}(\theta)+L_{r}(\theta)
$$
where the losses penalizes initial condition, boundary condition, and residual at interior collocation points separately.
- obtain the mesh-free solution
$$
\theta^{*}=\arg\min_{\theta}L(\theta)
$$

**PINN for Inverse Problems**
For inverse problems, the PDE structure is assumed known, but some parameters are unknown. The problem is of the form
$$
\partial_{t}u(x,t)+Q[u(x,t);\lambda]=0
$$
where $\lambda$ are unknown latent parameters. The goal is to identify both:
- the state $u(x,t)$,
- the parameters $\lambda$.

In this case, the loss is comprised of:
$$
L(\theta,\lambda)=L_{d}(\theta)+L_{f}(\theta, \lambda)+L_{\mathrm{physics}}(\theta)
$$
with data matching, residual loss, and any physics constraints known.


[[Deep Learning]]

