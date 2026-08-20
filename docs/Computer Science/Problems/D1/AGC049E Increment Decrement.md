## Step 1

We first consider the case where all $|S_i| = 1$.  We have a interval operation, so we can do it on the differential. Operations:
1. $d_i \rightarrow d_i \pm 1, d_{i+1} \rightarrow d_{i+1} \mp 1$ (cost $1$)
2. $d_i \rightarrow d_i \pm 1, d_{i+L-1} \rightarrow d_{i+L-1} \mp 1$ (cost $c$)
For any segment we choose that is shorter than $c$, we always choose operation 1.

We can merge the operations into 1:
$$d_i \rightarrow d_i \pm 1, d_{i+L-1} \rightarrow d_{i+L-1} \mp 1$$ Cost $\max(L, c)$.

## Step 2

Now how do we find the minimum cost?