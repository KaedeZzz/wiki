---
source: KaedeSync/_Knowledge/Computer Vision/Camera/Perspective Projection.md
ingested: 2026-07-06
---

Let $\mathbf{X}_{c}=(X_{c},Y_{c},Z_{c})$ for the visible world point, and $\mathbf{x}=(x,y)$ be the corresponding image plane point, both measured in the camera-centred coordinate system. (that is, $Z_{c}$ is along the optical axis)

![[Pasted image 20251102122315.png]]

Planar (2D) view:

![[Pasted image 20251102122356.png]]

$$
\frac{x}{f}=\frac{X_{c}}{Z_{c}}\implies x= \frac{fX_{c}}{Z_{c}}
$$
similarly for $y$ we have
$$
y=\frac{fY_{c}}{Z_{c}}
$$
[[Projection]]