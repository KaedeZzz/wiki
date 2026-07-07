---
source: KaedeSync/_Knowledge/Physics/Mechanics/Dynamical Systems/Koopman Operator Theory/Koopman Operator.md
ingested: 2026-07-06
---

[[Mechanics and Dynamics]]
Consider a discrete-time [[Dynamical System as Differential Equation]]
$$
u_{k+1}=F(u_{k})
$$
The Koopman operator $\mathcal K$ acts on the space of observables $g(u)$ and is defined by
$$
\mathcal K_{t}g=g \circ F_{t}
$$
where $\circ$ is the composition operator. See: [[Flow Map]]
For a discrete-time system with timestep $\Delta t$, this becomes:
$$
\mathcal K_{\Delta t}g(x_{k})=g(F_{\Delta t}(x_{k}))=g(x_{k+1})
$$
In other words, the Koopman operator defines an ***infinite-dimensional*** linear dynamical system that advances the observation of the state $g_{k}=g(x_{k})$ to the next time step:
$$
g(x_{t+1})=K_{\Delta t}g(x_{k})
$$
which is true for *any* observable function $g$ and any state $x_{k}$.

![[Linearity of Koopman Operator]]

(Continuous) operator $\mathcal K$ is the *infinitesimal generator of the one-parameter family of transformations* $\mathcal K_{t}$.
$$
\mathcal Kg=\lim_{ t \to 0 } \frac{K_{t}g-g}{t}=\lim_{ t \to 0 } \frac{g\circ F_{t}-g}{t}
$$
