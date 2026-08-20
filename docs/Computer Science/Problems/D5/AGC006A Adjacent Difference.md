## Hint

Since there is a $\frac{1}{2}$ in the minimum expression, we can try to construct 2 methods that sum to $dn^2$ and pick the minimum.

## Step 1

Obviously we try to use a checkerboard pattern. If we try to only correct black/white, there will be at most $3d-2$ cost per square. That adds up to $(\frac{3}{2}d - 1)n^2$.

## Step 2

We can try to adjust 1 side to $\bmod 2d = 0 / d$. The sum of the 2 cases is exactly $nd^2$, so problem solved.