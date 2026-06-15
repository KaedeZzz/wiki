---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Linear Models/ML Estimation of Linear Gaussian Model.md"
ingested: 2026-06-09
---

In the linear Gaussian/Gaussian-Markov model we have:
$$
\mathbf{x}=\mathbf{G\theta}+\mathbf{e}
$$
where the noise terms are i.i.d. zero-mean [[Gaussian Distribution]]s:
$$
p(\mathbf{e})=\prod_{n=0}^{N-1}\mathcal N(e_{n}|0,\sigma_{e}^{2})
$$
we can recognise the **distribution of error vector** as a [[Multivariate Gaussian]] with mean $\mathbf{0}$ and covariance matrix $\sigma_{e}^{2}\mathbf{I}$:
$$
p(\mathbf{e})=\mathcal N(\mathbf{e}|\mathbf{0},\sigma_{e}^{2}\mathbf{I})
$$

**ML Estimator**
To get to the likelihood function $p(\mathbf{x}|\mathbf{\theta})$, notice that the linear model equation $\mathbf{x}=\mathbf{G\theta}+\mathbf{e}$ is a vector change of variables $\mathbf{e}\to \mathbf{x}$. Hence:
$$
\mathcal L(\mathbf{x};\mathbf{\theta})=p(\mathbf{x}|\mathbf{\theta})=p(\mathbf{G\theta}+\mathbf{e}|\mathbf{\theta})=p(\mathbf{e})|_{\mathbf{e}=\mathbf{x}-\mathbf{G\theta}}=p_{\mathbf{e}}(\mathbf{x}-\mathbf{G\theta})
$$
Expansion gives:
$$
\begin{align}
p_{\mathbf{e}}(\mathbf{x}-\mathbf{G\theta}) & =\frac{1}{(2\pi\sigma_{e}^{2})^{N/2}}\exp\left( -\frac{1}{2\sigma_{e}^{2}}(\mathbf{x-\mathbf{G\theta}})^{T}(\mathbf{x-\mathbf{G\theta}}) \right)
\end{align}
$$
Taking log:
$$
\begin{align}
\log \mathcal L(x;\theta) & = -\frac{N}{2}\log(2\pi\sigma_{e}^{2})-\frac{1}{2\sigma_{e}^{2}}(\mathbf{x-\mathbf{G\theta}})^{T}(\mathbf{x-\mathbf{G\theta}})\\
 & =-\frac{N}{2}\log(2\pi\sigma_{e}^{2}) -\frac{1}{2\sigma_{e}^{2}}\sum_{n=0}^{N-1}(x_{n}-\mathbf{g}_{n}^{T}\mathbf{\theta})^{2} \\
 & =-\frac{1}{2\sigma_{e}^{2}}\sum_{n=0}^{N-1}(x_{n}-\mathbf{g}_{n}^{T}\mathbf{\theta})^{2}+Const.
\end{align}

$$
Maximisation of this function is thus minimisation of **sum-squared of the error sequence**, which is exactly the criterion applied in the [[OLS Estimator of General Linear Model]]. Hence the ML estimator is:
$$
\mathbf{\theta}^{ML}=\mathbf{\theta}^{OLS}=(\mathbf{G}^{T}\mathbf{G})^{-1}\mathbf{G}^{T}\mathbf{x}
$$

In general, when the error process $\{ e_{n} \}$ is zero-mean, independent and Gaussian with fixed variance, the OLS and ML solutions are *identical*. However, we would get a different solution if the noise were non-white and/or non-Gaussian; such models require a case-by-case ML analysis.

**Estimate the Noise Variance**
Consider the log-likelihood function at the optimal parameter estimate $\mathbf{\theta}^{ML}$, now considered as a function of $\sigma_{e}^{2}$:
$$
\begin{align}
\log \mathcal L(\mathbf{x};\mathbf{\theta}^{ML},\sigma_{e}^{2}) & =-\frac{N}{2}\log(2\pi\sigma_{e}^{2})-\frac{1}{2\sigma_{e}^{2}}(\mathbf{x}-\mathbf{G\theta}^{ML})^{T}(\mathbf{x}-\mathbf{G\theta}^{ML}) \\
 & =-\frac{N}{2}\log(2\pi\sigma_{e}^{2})-\frac{1}{2\sigma_{e}^{2}}J^{ML}
\end{align}
$$
Differentiate with respect to $\sigma_{e}^{2}$ and set to zero:
$$
\frac{{\partial\log \mathcal L(\mathbf{x};\mathbf{\theta}^{ML},\sigma_{e}^{2})}}{\partial\sigma_{e}^{2}}=-\frac{N}{2\sigma_{e}^{2}}+\frac{J^{ML}}{2(\sigma_{e}^{2})^{2}}=0
$$
we get
$$
{\sigma_{e}^{2}}^{ML}=\frac{J^{ML}}{N}
$$
i.e. the [[Mean Squared Error]] at the ML parameter solution.

[[Maximum Likelihood Estimation]], [[General Linear Model (GLM)]]