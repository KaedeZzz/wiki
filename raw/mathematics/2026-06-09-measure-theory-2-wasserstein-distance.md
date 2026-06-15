---
source: "KaedeSync/_Knowledge/Mathematics/Measure Theory/2-Wasserstein Distance.md"
ingested: 2026-06-09
---

Let $\mu, \nu$ be [[Probability Measure]]s on $\mathbb{R}^{d}$ (or a metric space) with finite second moments. Define the set of couplings. The 2-Wasserstein distance is defined as:
$$
W_{2}(\mu, \nu)=\left(\inf_{(X,Y):X\sim \mu, Y\sim \nu}\mathbb{E}\lVert  X-Y \rVert^{2} \right)^{1/2}
$$
In other words, it attempts to match a draw from $\mu$ to a draw from $\nu$ so that the expected squared distance is as small as possible.