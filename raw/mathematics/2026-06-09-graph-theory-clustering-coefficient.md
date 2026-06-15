---
source: "KaedeSync/_Knowledge/Mathematics/Graph Theory/Clustering Coefficient.md"
ingested: 2026-06-09
---

Measures the density of triangles in a [[Graph]].

If node $i$ has degree $k_{i}$, then it could have a maximum of $\frac{1}{2}k_{i}(k_{i}-1)$ triangles, hence the local clustering coefficient is:
$$
c_{i}=\frac{{\frac{1}{2}\sum_{jk}A_{ij}A_{ik}A_{jk}}}{\frac{1}{2}k_{i}(k_{i}-1)}=\frac{{\sum_{jk}A_{ij}A_{ik}A_{jk}}}{k_{i}(k_{i}-1)}
$$
Then, the clustering coefficient for a graph can be defined as the average of this quantity:
$$
c = \frac{1}{n}\sum_{i}\frac{{\sum_{jk}A_{ij}A_{ik}A_{jk}}}{k_{i}(k_{i}-1)}
$$
Another definition for the clustering coefficient, sometimes called global clustering coefficient, is the total number of triangles divided by the largest possible number:
$$
c=\frac{{\sum_{i,j,k}A_{ij}A_{jk}A_{ki}}}{\sum_{i}k_{i}(k_{i}-1)}
$$
