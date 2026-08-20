## Factorization

Number of Factors: $O(n^\frac{1}{3})$, sieve up to $n^\frac{1}{3}$, and check if the remaining is a perfect square.

Cumulative Sum of Factor Count Calculation: $O(\sqrt{n})$, Division Cumsum.

Prime Factorization: Treat as a vector of exp.

## Sieves

Bell Series:
For a multiplicative function $f$ and a prime $p$, its series is:
$$F_p(x) = \sum_{k \ge 0}{f(p^k)x^k}$$

| Function      | Series                     |
| ------------- | -------------------------- |
| $\epsilon$    | 1                          |
| $I$           | $\frac{1}{1-x}$            |
| $\mu$         | $1-x$                      |
| $\mu^2$       | $1+x$                      |
| $\lambda$     | $\frac{1}{1+x}$            |
| $\text{id}_k$ | $\frac{1}{1-p^k x}$        |
| $\sigma_k$    | $\frac{1}{(1-p^k x)(1-x)}$ |
| $\varphi$     | $\frac{1-x}{1-px}$         |
If $h = f * g$, then $H_p(x) = F_p(x) G_p(x)$

We use Dirichlet Convolution:
$$(f*g)(x) = \sum_{d|x}{f(x)g(\frac{d}{x})}$$
## Modular Arithmetic

### Primitive Root

#### Order

The function $f(n) = a^n \mod p$ has a period. We call the period $\text{ord}(a) = T$.

#### Primitive root

If $\text{ord}(g) = \varphi(p)$, then $g$ is a primitive root of $p$. Primitive roots only exist for: $\{1, 2, 4, p^k, 2p^k\}$.

If a primitive root exists, let $x \equiv g^a$:
$$\text{ord}(x) = \frac{\varphi(m)}{\gcd(a,\varphi(m))}$$

### Power Tower

#### Euler's Theorem

$$a^n \equiv \begin{cases}
a^n, n < \varphi(m) \\
a^{(n \bmod \varphi(m)) + \varphi(m)}
\end{cases} \pmod{m}$$
If $a \perp m$, then this simplifies to:
$$a^n \equiv a^{n \bmod \varphi(m)} \pmod{m}$$
### Misc.

#### Modular Subset Sum

### Combinatorics

#### Lucas

$$\binom{n}{k} \equiv \binom{n \bmod p}{m \bmod p} \binom{\left\lfloor\frac{n}{p}\right\rfloor}{\left\lfloor\frac{m}{p}\right\rfloor} \pmod{p}$$
#### Kummer

$$\begin{align}
v_p\left(\binom{n}{k}\right) 
& = \# \text{ of times we have to borrow when calculating } (n - k) \text{ under } \bmod p \\
& = \frac{S_p(k) + S_p(n - k) - S_p(n)}{p - 1}
\end{align}$$
where $S_p(x) = S_p\left(\left\lfloor\frac{x}{p}\right\rfloor\right) + (x \bmod p)$.

#### Legendre's Formula

$$v_p(n!) = \sum_{k=0}^\infty{\left\lfloor \frac{n}{p^k} \right\rfloor} = \frac{n - S_p(x)}{p-1}$$
#### Vandermonde Convolution

$$\sum_{r=0}^k{\binom{n}{r}\binom{m}{k-r}} = \binom{n + m}{k}$$
