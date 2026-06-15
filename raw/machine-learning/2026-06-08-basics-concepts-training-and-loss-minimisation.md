---
source: KaedeSync/_Knowledge/Machine Learning/Basics/Concepts/Training and Loss Minimisation.md
ingested: 2026-06-08
---

Train parameters $\theta$ to minimise the expected [[Loss Function]], $\mathcal L_{act}$:
$$
\mathcal L_{act}=\int\left[\sum_{i=1}^{K}\mathcal L(f(x,\theta),\omega_{i})P(\omega_{i}|x)\right]p(x)dx
$$
where $p(\omega_{i}|x)$ is the "true" probability of class given observation and $p(x)$ is the "true" probability of an observation. Neither of these are usually known.
Instead, we may have samples drawn from $p(\omega,x)=P(\omega|x)p(x)$ -- the (supervised) training data $\mathcal D$.
Creating training data:
1. obtain $x_{i} \sim p(x)$
2. create label $y_{i} \sim P(\omega|x_{i})$
This yields supervised training data: see [[Supervised & Unsupervised Learning]]
$$
\mathcal D=\{ \{ x_{1},y_{1} \},\dots ,\{ x_{n},y_{n} \} \}
$$
$x_{i}$: the observation, feature vector
$y_{i} \in \{ \omega_{1},\dots,\omega_{K} \}$: class label for observation $x_{i}$

Note that we care about performance on unseen data: split data for training and evaluation
***Training loss function could be different from test loss to measure performance.***
