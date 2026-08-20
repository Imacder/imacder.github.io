Count non intersecting paths in a DAG.

## Basic Description

Given a set of start nodes $S_i$, and end nodes $T_i$. Let:
$$M_{ij} = \sum_{P:S_i \rightarrow T_j}{\omega(P)}$$
(The sum of weights for all paths $P$.) $\omega$ is defined as the product of edge weights. Then:
$$\det(M)=\sum_{\pi}{\text{sgn}(\pi)\sum_{\substack{P[1\dots k] \text{ non intersecting} \\ P_i: S_i \rightarrow T_{\pi_i}}}{\prod _{i=1}^{n}\omega(P_i)}}$$
The "non intersecting" part is implicit. The original determinant definition includes both intersecting and non-intersecting. However, every intersecting path combo can form a bijection with another intersecting path combo (of different sign), therefore they all cancel. The bijection can be formed by switching the path ownership of the first intersection point.

## Application

Notice that when we set $\omega(P) = 1$ for all $P$, $M_{ij}$ is just the number of paths from $S_i$ to $T_j$, and the product term in the determinant drops out as well.
$$\det(M)=\sum_{\pi}{\text{sgn}(\pi)\sum_{\substack{P[1\dots k] \text{ non intersecting} \\ P_i: S_i \rightarrow T_{\pi_i}}}{1}}$$
If any inversions of $\pi$ will cause the paths to intersect, then we can simplify:
$$\det(M) = \sum_{\substack{P[1\dots k] \text{ non intersecting} \\ P_i: S_i \rightarrow T_{\pi_i}}}{\prod _{i=1}^{n}\omega(P_i)}$$
If a problem satisfies both conditions, then $\det(M)$ basically becomes the number of non-intersecting paths combinations from $S_i$ to $T_i$!

The can give us a $\mathcal{O}(k^3)$ method to solve this kind of problem.