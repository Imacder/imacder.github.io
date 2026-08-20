## Step 1

If we sort $x$ in ascending order, $y$ must be descending.
therefore to calculate the sum of the areas, we can simply do:
$$\Delta V = (x_i-x_j)y_i - a_i$$
This can be directly translated to a dp:
$$f[i] = \max_{j < i}{\{(x_i - x_j)y_i-a_i+f[j]\}}$$
## Step 2

Use the Slope Optimization.
$$f[i] = \max_{j<i}{\{-y_i x_j + f[j]\}} + x_i y_i - a_i$$
$$-y_i x_j + f[j] = b$$
$$y_i x_j + b = f[j]$$
We maintain a convex hull of $(x_j, f[j])$, and slide a line of slope $y_i$ from $b = + \infty$ to intercept the hull. That is the $b$ we need.