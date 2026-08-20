## Problem

Given $d$, find all $(x,y)$ such that:
$$x^2 + y^2 = d$$
## Initial Thoughts

We can split into odd and even cases:

### EE

$$(2u)^2 + (2v)^2 = d$$
$$d \bmod 4 = 0$$
### EO
$$(2u+1)^2 + (2v)^2 = d$$
$$4(u^2+u+v^2) + 1 = d$$
$$d \bmod 4 = 1$$
### OO
$$(2u+1)^2 + (2v+1)^2 = d$$
$$4(u^2 + v^2 + u + v) + 2 = d$$
$$d \bmod 4 = 2$$
If $d \bmod 4 = 3$, there is no solution.

### Observation

We consider the case where we have reduced all EE to EO or OO.

### OO

All solutions are odd. If we build vectors on $(x,y)$ to span the plane, we can track the parity of $x$ or $y$ (either will do) and color based on its parity.

### EO

Same idea, only now we track the parity of $x+y$ because it is odd and color accordingly.

Therefore, all $d$s leads to bipartite graphs.

## Gaussian Primes

If we want to find **ALL** integer solutions of the equation, we can do prime factorization in the gaussian field $\mathbb{Z}[i]$.

We transform the problem into this:
Find all gaussian integers $z$ such that:
$$z \bar{z} = d$$

A prime $p > 2$ can be decomposed into 2 gaussian primes iff $p \bmod 4 = 1$. By performing factorization, we get the number of solutions.

If $d = 2^k \prod{p_i^{e_i}}, p_i \in \mathbb{P},p_i>2$ (normal factorization of over $\mathbb{Z}[1]$), the number of solutions is:
$$4 \prod_{p_i \bmod 4 = 1}{(e_i + 1)} \prod_{p_i \bmod 4 = 3}{[e_i \bmod 2 = 0]}$$

The $4$ factor is because we can choose to multiply the number by $\{1,-1,i,-i\}$. Note that $2 = (1 + i)(1 - i)$ so it is factorizable. However $\frac{1+i}{1-i} = i$, so it generates the same operations we collapsed into the $4$ factor. Therefore number of $2$s we have doesn't matter.

## Extension to Multiplicative Functions

We find that the solution above is correct, but is also very messy. Therefore we can try to find a better one. We can try to construct a multiplicative function:

$$f(p^k) = \begin{cases}
1, &p = 2\\
k \bmod 2, &p \bmod 4 = 3 \\
k + 1, &p \bmod 4 = 1
\end{cases}$$
Notice that this function can be broken down rather elegantly:
Define:
$$\chi(x)=\begin{cases}
1, &x \bmod 4 = 1 \\
0, &x \bmod 2 = 0 \\
-1, &x \bmod 4 = 3 \\
\end{cases}$$
This is Dirichlet Character $\chi_4$. Then:
$$f(p^k) = \sum_{i=0}^k{\chi(p^i)}$$
If we write $d = \prod{p_i^{e_i}}, p_i \in \mathbb{P}$,
$$f(d) = \prod{f(p_i^{e_i})} = \prod{\sum_{k=0}^{e_i}{\chi{p^k}}} = \sum_{x | d}{\chi(x)}$$
What an elegant way to calculate the solution count!

## Pi

If we are able to count the points on the edge of the circle, we are able to estimate its area.

$$\begin{align}\text{Area} &= \pi r^2 \\&\approx 1 + 4\sum_{d = 1}^{r^2}{f(d)} \\&= 1 + 4\sum_{d = 1}^{r^2}{\sum_{x | d}{\chi(x)}} \\&= 1 + 4\sum_{x = 1}^{\infty}{\chi(x)\sum_{x | d, d \le r^2}}{1} \\&= 1 + 4\sum_{x = 1}^{\infty}{\chi(x) \left\lfloor \frac{r^2}{x} \right\rfloor} \\&\approx 4r^2 \sum_{x = 1}^{\infty}{\chi(x)\frac{1}{x}} \\&= 4r^2 \sum_{k=1}^{\infty}{\frac{1}{2k - 1}}\end{align}$$

Then if we rearrange a bit:

$$\frac{\pi}{4} = \sum_{k = 1}^{\infty}{\frac{1}{2k-1}}=1-\frac{1}{3}+\frac{1}{5}-\frac{1}{7}+\cdots$$
