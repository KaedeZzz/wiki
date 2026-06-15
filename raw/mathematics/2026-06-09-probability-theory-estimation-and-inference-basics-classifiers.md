---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Basics/Classifiers.md"
ingested: 2026-06-09
---

[[Machine Learning]]
Generative models: 
model $p(x,\omega,\theta)$. The posterior is then obtained from [[Bayes Theorem]]:
$$
p(w_{i}|x^{*},\theta)=\frac{p(x^{*},\omega_{i},\theta)}{\sum_{j=1}^{K}p(x^{*},\omega_{j},\theta)}
$$

Discriminative models: 
$P(\omega|x^{*},\theta)$ is trained.

Discriminant functions: 
A mapping $x^{*}\to \omega$ is directly trained, no probabilities.
Example: [[Support Vector Machine]]

**Why we use discriminative classifiers?**
If we use discriminative models, we only need to learn [[Decision Boundary]]. However if we use generative models, we need to learn joint probability of all data, which is more complex. 
However, generative data may be more data efficient.