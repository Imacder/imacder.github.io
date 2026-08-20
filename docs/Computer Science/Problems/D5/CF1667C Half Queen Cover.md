## Step 1

We can get a lower bound on the problem. Using $k$ queens, we can cover everything except a "square" $(n-k) \times (n-k)$. We can try to cover the rest with the diagonal. There are $2(n-k)-1$ diagonals left. Putting them together we find $\left\lceil \frac{2n-1}{3} \right\rceil$.

## Step 2

We can find a solution for $n \equiv 2 \pmod 3$. Then we fill the last 2 L shapes with 2 queens on the diagonal. 