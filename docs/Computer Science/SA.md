## Definition

$\text{sa}[i]$ is the $i$th lexicographically smallest suffix of $s$.
$\text{rk}[i]$ is the lexicographical order of suffix $s[i \dots n]$.
They are inverses of one another.

$h[i] = \text{lcp}(\text{sa}[i], \text{sa}[i - 1])$.
It follows that $\text{lcp}(\text{sa}[i], \text{sa}[j]) = \min{h[i + 1 \dots j]}$.

## Construction

We batch up adjacent blocks of $2^k$. Because the previous step has it already sorted, we can just use the result. We'll also use bucket sort for the inner layer for efficiency.

Specifically, we use radix sort, but we use stable sort for the first digit and therefore we don't have to sort the second layer.

For height we have:
$$h[\text{rk}[i]] \ge h[\text{rk}[i - 1]] + 1$$
We can just brute force with this.