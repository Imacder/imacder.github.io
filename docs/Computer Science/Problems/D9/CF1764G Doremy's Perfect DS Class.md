## Step 1

Understand the problem:
When we choose $k$, we split the permutation into multiple groups:
$$[1, k-1],[k,2k-1],\dots,[mk, n]$$
There are only 2 groups that (may) have a size not equal to k:
$$[1, k-1], [mk, n]$$
The first have a size of $k-1$, the second has a size of $n \bmod k + 1$.

## Step 2

The problem suggests $\log_2$ scale, and $k>2$ is hard to deal with, therefore we'll choose $k=2$ for the queries. We can consider how to binary search.

Note: We do not use typical binary search, we instead put the current $\text{mid}$ into the entire sequence to check for viability. This is because there is no direct way to query a subsequence when there could be fractured groups inside. The $\text{mid}$ here is **NOT** the middle of $[1, n]$.

We can query $[1, \text{mid}]$ and $[\text{mid} + 1, n]$. For each of the groups, they will fall into the following categories:
1. Both are on the left side. (count $a$)
2. Both are on the right side. (count $b$)
3. There's one on each side. (count $c$)
4. $1$. ($d$)
5. $n$. ($e$, this only appears when $n$ is even)

We first solve the easy case when $n$ is odd.
$$
\begin{cases}
a + c + d_l = Q_l \\
b + c + d_r = Q_r \\
2a + c + d_l = \text{mid} \\
2b + c + d_l = n - \text{mid} \\
d_l + d_r = 1
\end{cases}
$$
We can solve the equation to know which side $1$ is on. Then the binary search is trivial.

When $n$ is even, the situation is more complex:

We can first binary search out where $n$ is, but this only passes G1.
$$
\begin{cases}
a + c + d_l + e_l = Q_l \\
b + c + d_r + e_r = Q_r \\
2a + c + d_l + e_l = \text{mid} \\
2b + c + d_l + e_l = n - \text{mid} \\
d_l + d_r = 1 \\
e_l + e_r = 1
\end{cases}
$$
This is arguable more complex. And the equation became unsolvable. We can consider treating $d_l + e_l$, and $d_r + e_r$ as a whole. Then the equation is solvable. If $d_l + e_l$ is $0$ or $2$, we know that $1$ and $n$ are on the same side and we can search. If it's $1$, then there is one on each side. We can check this $\mathcal{O}(1)$ with $[1, \text{mid}]$ and $k=n$ (which splits $n$ into its own group.) With this method we can pass G1 with $21$ queries.

## Step 3

The final optimization.

We can shave of $1$ query when $[l, r]$ is size $2$. If we still haven't distinguished between $1$ and $n$, we simply check.

Otherwise, we have already queried $[1,l−1],[1,r],[l,n],[r+1,n]$. We can use this along with $[r, n]$ to deduce the answer.

See [here](https://www.luogu.com.cn/article/ul8bwuuh).