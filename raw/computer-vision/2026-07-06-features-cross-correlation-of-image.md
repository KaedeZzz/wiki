---
source: KaedeSync/_Knowledge/Computer Vision/Features/Cross Correlation of Image.md
ingested: 2026-07-06
---

The normalized cross-[[Correlation]] function measures how well an image patch $P(x,y)$ matches other portions of the image $I(x,y)$ as it is shifted from its original location.
$$
c(x,y)=\frac{{\sum_{u=-n}^{n}\sum_{v=-n}^{n}P(u,v)I(x+u,y+v)}}{\sqrt{\sum_{u=-n}^{n}\sum_{v=-n}^{n}P^{2}(u,v)\sum_{u=-n}^{n}\sum_{v=-n}^{n}I^{2}(x+u,y+v) }}
$$
A patch which has a **well-defined peak** in its correlation function can be classified as a corner.

[[Image Features]]