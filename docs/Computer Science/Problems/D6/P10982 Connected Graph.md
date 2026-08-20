## Step 0

**This is a WRONG idea.**

We first set $f(i)$ to represent the number of undirected graphs of $i$ vertices. Then naively we can define $g(i,j)$ to mean the number of graphs of $i$ vertices that have a connected component of at least size $j$.

$$g(i,j) = \binom{i}{j}f(j)2^{\binom{i}{2} - \binom{j}{2}}$$
However, this definition of $g$ is incorrect. For a graph with 2 $j$-sized connected component, the graphs gets counted twice (once for each component.)

An obvious fix for this is to remove the $\binom{i}{j}$ from $g$. Then $g$ wouldn't overcount and would instead correctly represent the number of graphs of $i$ vertices with $[1, j]$ as a connected component. However, this messes up $f$ computation, so this is a dead end.

## Step 1

We first set $f(i)$ to represent the number of undirected graphs of $i$ vertices. Set $g(i)$ to represent the number of **connected** undirected graphs of $i$ vertices.

We want:
$$g(n) = f(n) - (\# \text{ of graphs that are unconnected})$$

## Step 2

To avoid over counting, we still apply the idea in step 0. We can only iterate over the component size of $s$ that contains $1$.
$$g(n) = 2^{\binom{n}{2}} - \sum_{j=1}^{n-1}{g(j) \binom{n-1}{j-1} 2^{\binom{n-j}{2}}}$$
