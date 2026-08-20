## Step 1

$$\sum_{x \in S}{\prod{x_i}} = \sum_{b_i \le a_i}{\prod{(a_i - b_i + b_{i-1})}}$$
without the distinct constraint. The distinct constraint can be seen as there is at least 1 $b_i = 0$.

## Step 2

$$
\begin{align}
&f[m] \\ =&
\sum_{b[1 \dots m]}{\prod_{1 \le i \le m}{(a_i - b_i + b_{i - 1})}} \\ =&
\sum_{b[1 \dots m-1]}{\sum_{0/1 \le b_m \le a_m}{(a_m - b_m + b_{m-1})\prod_{1 \le i \le m-1}{(a_i - b_i + b_{i-1})}}} \\ =&
\sum_{0/1 \le b_m \le a_m}{\sum_{b[1 \dots m-1]}{\left( (a_m - b_m)\prod_{1 \le i \le m-1}{(a_i - b_i + b_{i-1})} + b_{m-1}\prod_{1 \le i \le m-1}{(a_i - b_i + b_{i-1})} \right)}} \\ =&
\sum_{0/1 \le b_m \le a_m}{(a_m - b_m) \sum_{b[1 \dots m-1]}{\prod_{1 \le i \le m-1}{(a_i - b_i + b_{i-1})}}} + (a_m + 1/0) \sum_{b[1 \dots m-1]}{b_{m-1}\prod_{1 \le i \le m-1}{(a_i - b_i + b_{i-1})}} \\=&
\left(\sum_{0/1 \le b_m \le a_m}{(a_m - b_m)}\right)\left(\sum_{b[1 \dots m-1]}{\prod_{1 \le i \le m-1}{(a_i - b_i + b_{i-1})}}\right) + (a_m + 1/0) \sum_{b[1 \dots m-1]}{b_{m-1}\prod_{1 \le i \le m-1}{(a_i - b_i + b_{i-1})}} \\ =&
s_1[m] \cdot f[m-1] + s_2[m] \cdot g[m-1]
\end{align}
$$

$$
\begin{align}
&g[m] \\ =&
\sum_{b[1 \dots m]}{b_m \prod_{1 \le i \le m}{(a_i - b_i + b_{i - 1})}} \\ =&
\sum_{0/1 \le b_m \le a_m}{\sum_{b[1 \dots m-1]}{\left( b_m(a_m - b_m)\prod_{1 \le i \le m-1}{(a_i - b_i + b_{i-1})} + b_mb_{m-1}\prod_{1 \le i \le m-1}{(a_i - b_i + b_{i-1})} \right)}} \\ =&
\sum_{0/1 \le b_m \le a_m}{b_m(a_m - b_m) \sum_{b[1 \dots m-1]}{\prod_{1 \le i \le m-1}{(a_i - b_i + b_{i-1})}}} + \sum_{0/1 \le b_m \le a_m}{b_m\sum_{b[1 \dots m-1]}{b_{m - 1}\prod_{1 \le i \le m-1}{(a_i - b_i + b_{i-1})}}} \\ =&
\left(\sum_{0/1 \le b_m \le a_m}{b_m(a_m - b_m)}\right)\left(\sum_{b[1 \dots m-1]}{\prod_{1 \le i \le m-1}{(a_i - b_i + b_{i-1})}}\right) + \left(\sum_{0/1 \le b_m \le a_m}{b_m}\right)\left(\sum_{b[1 \dots m-1]}{b_{m - 1}\prod_{1 \le i \le m-1}{(a_i - b_i + b_{i-1})}}\right) \\ =&
s_3[m] \cdot f[m-1] + s_4[m] \cdot g[m-1]
\end{align}
$$

We can set $b_0 = b_n = x$, and iterate through $[1 \dots n-1]$. At $m = n$, we can only calculate $f[n]$:
$$
\begin{align}
&f[n] \\ =&
\sum_{0/1 \le b_n \le a_n}{(a_n - b_n) \sum_{b[1 \dots n-1]}{\prod_{1 \le i \le n-1}{(a_i - b_i + b_{i-1})}}} + \sum_{0/1 \le b_n \le a_n}{\sum_{b[1 \dots n-1]}{b_{n-1}\prod_{1 \le i \le n-1}{(a_i - b_i + b_{i-1})}}} \\ =&
\sum_{0/1 \le x \le a_n}{\left((a_m - x) \cdot f[n - 1](x) + g[n - 1](x)\right)}
\end{align}
$$
## Another Solution (Kimi K3)

### Setup

Let $b_i \in [0, a_i]$ be the number of balls person $i$ passes. Then

$$x_i = a_i - b_i + b_{i-1} \quad (\text{indices mod } N)$$

Your reduction is correct, and it's worth stating why: $x$ is unchanged if we shift **all** $b_i$ by the same constant, and conversely two vectors $b, b'$ give the same sequence iff $b - b'$ is constant (since $x_i = x_i'$ forces $b_i - b_i' = b_{i-1} - b_{i-1}'$ for all $i$, i.e. constant around the cycle). So each sequence in $S$ has **exactly one** representative with $\min b_i = 0$, and

$$\text{answer} = \sum_{b:\ \min b = 0} \prod_i x_i = U - U_{\ge 1}$$

where $U$ is the unconstrained sum over all $b$, and $U_{\ge 1}$ is the sum over $b$ with every $b_i \ge 1$.

### Unconstrained sum $U$

$$U = \sum_{b_1=0}^{a_1}\cdots\sum_{b_N=0}^{a_N} \prod_{i=1}^{N}\big((a_i - b_i) + b_{i-1}\big)$$

Expand the product: for each factor $i$ choose one of the two terms. Encode the choices by $S \subseteq [N]$ ($i \in S \Leftrightarrow$ take $a_i - b_i$). The key observation: **$b_i$ appears in at most two chosen terms**, and which ones is determined by the membership of $i$ and $i+1$ in $S$. So the inner sum over $b$ factorizes per person:

| status of $i$ | status of $i+1$ | local factor |
|---|---|---|
| in | in | $\sum_{b}(a_i-b) = \binom{a_i+1}{2}$ |
| in | out | $\sum_{b}(a_i-b)\,b = \binom{a_i+1}{3}$ |
| out | in | $\sum_{b} 1 = a_i+1$ |
| out | out | $\sum_{b} b = \binom{a_i+1}{2}$ |

(Sanity: $\sum_{b=0}^{a}(a-b)b = \frac{a^2(a+1)}{2} - \frac{a(a+1)(2a+1)}{6} = \frac{(a-1)a(a+1)}{6} = \binom{a+1}{3}$.)

So with the $2\times 2$ transfer matrix (row = status of $i$, column = status of $i+1$):

```
M_i = [ C(a_i+1,2)   C(a_i+1,3) ]
      [ a_i+1        C(a_i+1,2) ]
```

the sum over all subsets $S$ around the circle is exactly a trace:

$$U = \operatorname{tr}(M_1 M_2 \cdots M_N)$$

### The constrained part $U_{\ge 1}$

Same expansion, but $b_i$ now ranges over $[1, a_i]$. **Warning:** $x_i$ still contains $a_i$ (don't replace $a_i$ by $a_i - 1$ inside $x_i$ — shifting all $b$'s by 1 leaves $x$ invariant, it doesn't shift $a$). Only the local sums change, and since the terms $(a_i-b)b$ and $b$ vanish at $b=0$ anyway, only two entries change:

```
M'_i = [ C(a_i,2)    C(a_i+1,3) ]
       [ a_i         C(a_i+1,2) ]
```

### Final formula

$$\boxed{\ \text{ans} = \operatorname{tr}\Big(\prod_i M_i\Big) - \operatorname{tr}\Big(\prod_i M'_i\Big) \pmod{998244353}\ }$$

$O(N)$ time, $O(1)$ memory (two running $2\times2$ products). Note $a_i = 0$ makes $M'_i$ the zero matrix, correctly forcing $U_{\ge 1} = 0$.

### Verification

- $a=(1,1,1)$: $M=\begin{pmatrix}1&0\\2&1\end{pmatrix}$, $\operatorname{tr}M^3 = 2$; $M'=\begin{pmatrix}0&0\\1&1\end{pmatrix}$, $\operatorname{tr}M'^3 = 1$; ans $= 1$ ✓ (only $(1,1,1)$ has nonzero product in the sample's $S$).
- $a=(2,2)$: $\operatorname{tr}M^2 = 24$, $\operatorname{tr}M'^2 = 14$, ans $= 10$. Brute force: $S = \{(0,4),(1,3),(2,2),(3,1),(4,0)\}$, $\sum\prod = 0+3+4+3+0 = 10$ ✓.
- $N=1$: $x_1 = a_1$ always, ans $= a(a+1) - a^2 = a$ ✓.

### Code

```cpp
#include <bits/stdc++.h>
using namespace std;
using ll = long long;
const ll MOD = 998244353, INV2 = 499122177, INV6 = 166374059;

struct Mat { ll a00, a01, a10, a11; };
Mat mul(Mat A, Mat B) {
    return { (A.a00*B.a00 + A.a01*B.a10) % MOD, (A.a00*B.a01 + A.a01*B.a11) % MOD,
             (A.a10*B.a00 + A.a11*B.a10) % MOD, (A.a10*B.a01 + A.a11*B.a11) % MOD };
}

int main() {
    int N; scanf("%d", &N);
    Mat P{1,0,0,1}, Q{1,0,0,1};
    for (int i = 0; i < N; i++) {
        ll a; scanf("%lld", &a); a %= MOD;
        ll c2 = a*(a+1)%MOD*INV2%MOD;                  // C(a+1,2)
        ll c3 = (a+MOD-1)%MOD*a%MOD*(a+1)%MOD*INV6%MOD; // C(a+1,3)
        ll d2 = (a+MOD-1)%MOD*a%MOD*INV2%MOD;          // C(a,2)
        P = mul(P, Mat{c2, c3, (a+1)%MOD, c2});
        Q = mul(Q, Mat{d2, c3, a, c2});
    }
    ll ans = (P.a00 + P.a11 - Q.a00 - Q.a11) % MOD;
    printf("%lld\n", (ans + MOD) % MOD);
}
```

A remark on *why* the state dimension is only 2: the kernel $x_i = u + (a_i - v)$ is a sum of two rank-1 terms in $(u, v) = (b_{i-1}, b_i)$, so the transfer matrix factorizes through a 2-dimensional space — equivalently, the subset expansion above only needs to remember one bit of "boundary" information per adjacent pair.