## Gaussian Elimination

(Skipped the basics.)

When doing this $\bmod m$ where an inverse might not exist, we can use a process similar to the Euclidean Algorithm. In the algorithm, we we repeatedly divide until one of $a$ $b$ is $0$.

Here we can swap in $a \bmod b$ for $a - \left\lfloor \frac{a}{b} \right\rfloor b$, and we do this for all the rows. $\left\lfloor \frac{a}{b} \right\rfloor$ is treated as a coefficient and doesn't need modular arithmetic.

## Xor Basis

### Merging

Xor basis supports merge $\mathcal{O}(\log^2(V))$, we simply insert all the basis into the other one.

### Prefix Basis?

We try to use the **LAST** position that gives a digit (so we need to maintain a $\text{pos}$ array of where the last of the positions occurred.) We can do this by swapping out the current $x$ for the one in the basis whenever possible. Then when we have to query a range, we simple skip all of those with $\text{pos} \ge l$.

### RREF Form

See [here](https://share.gemini.google/dtIP7H3YZq7d). This form has some very useful properties.

### Intersection of Basis

We do something similar to merging. But now when we insert $b_i$ into $A$, we also keep track of which basis vectors it used **IN $A$**. The unreduced part is added to the basis. If there isn't any leftover, add the xor sum of the tracked history to the intersection basis. This method simultaneously computes the intersection and the union.

### Some Random Properties

The span of $a[1..n]$ is equal to the span of $a[1] + (a[2..n] - a[1..(n-1)])$.