---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Distribution Sampling/Intuition of Rejection Sampling.md"
ingested: 2026-06-09
---

#ESSENTIAL 
[[Rejection Sampling]]
Imagine using a (uniform) distribution to **cap** the distribution we want to sample, *that is, height of uniform distribution = maximum value of sampled distribution*. 
1. Sample from uniform distribution, we have equal chances to obtain all $x$ values within range of input of target sampling distribution;
2. We set a **probability of acceptance** of every $x$ value being value of pdf divided by height of cap.
3. That is, when we get an $x$ where $f_{X}(x)$ is high, we highly likely accept it; when we get an $x$ where $f_{X}(x)$ is low, we very unlikely accept it. 
4. In this way, we get more $x$ values where value of pdf is high, thus doing a proper sampling of $f_{X}(x)$.