## Statement
Given sequence $A$. Find the minimum of:
$$\sum_{i=1}^n{|x_i|+|x_i-A_i|}$$
where $x_i - x_{i-1} \ge 0$, $(A_i - x_i) - (A_{i - 1} - x_{i - 1}) \le 0$.
## Step 1
$$(A_i - x_i) - (A_{i - 1} - x_{i - 1}) \le 0$$
$$\max(A_i - A_{i - 1}, 0) \le x_i - x_{i - 1}$$

