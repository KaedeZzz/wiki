---
source: KaedeSync/_Knowledge/Machine Learning/Deep Learning/Autoencoders/Variational Autoencoder.md
ingested: 2026-06-08
---

[[Auto-Encoding Variational Bayes, Kingma et al. (2022)]]

Why does [[Autoencoder]] not able to generate image directly?
A: Sampling latent vectors, even near input data, gives bad results; latent space is unorganised and irregular.
Solution: **organise latent space**

Target: generate new data from given data distribution $p(x)$.
Introduce **Latent Distribution**, that is, distribution of data in latent space, denoted as $p(z)$.
We need mapping between two distributions:
1. Posterior distribution $p(z|x)$
2. Natural distribution $p(x|z)$
Idea: [[Bayes Theorem]] 
$$
p(x)= \frac{p(x|z)p(z)}{p(z|x)}
$$

How to obtain the values?
Assume $p(z) \sim \mathcal N(0,1)$, then $p(x|z)$ is obtained
How to get $p(z|x)$?
Use a [[Gaussian Distribution]]: $q(z|x) = \mathcal N(\mu,\sigma)$ to approximate it, where $\mu$ and $\sigma$ are to be learned. 
The learning process is known as [[Variational Bayes]].

**My idea: essentially forcing/regulating each latent space to be Gaussian. Is it correct?**
We train an encoder to estimate $\mu$ and $\sigma$, and train a decoder to reconstruct data. How?

Loss Function: [[KL Divergence]]
$$
\begin{aligned}
\mathcal L(x)&=\mathbb{E}_{q(z|x)}\{\log p(x|z)\}+D_{KL}(q(z|x)|p(z))\\
&=L_{2}(x,x')+D_{KL}(\mathcal N(\mu,\sigma)|\mathcal N(0,1))
\end{aligned}
$$

That is: data consistency - latent space regularisation
This is EM!

How do we do in practice?
Essentially: transform a datapoint to a Gaussian distribution in latent space, and then generate image by sampling the latent distribution
![[Pasted image 20240912223911.png]]
However we **CANNOT DO BACKPROPAGATION** here.

Reparametrisation
Introduce $\epsilon$ (excellence) as an additional random variable to describe randomness.
$$
\epsilon\sim\mathcal N(0,1)\text{; sample from }\epsilon\text{ and decode }\mu+\sigma \cdot\epsilon
$$
This way, partial derivative can be done to $\mu$ and $\sigma$.

Pros:
1. Vectors near reference vectors (input data) DO generate similar images. Further vectors generate less similar images.
2. Latent space is continuous. Interpolation of two latent vectors DO generate something "between" two images. Compact and smooth latent space.
Cons:
1. Produce blurry images (because of loss function, not architecture)
2. Lack of ability to choose which image to generate

Variations:
[[CVAE]]
[[beta-VAE]]
[[VQ-VAE]]