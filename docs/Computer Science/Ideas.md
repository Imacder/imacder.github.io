1. If treap is only used to sort by key, we can do it offline with a segment tree
2. if minimization of a full permutation is too difficult, try minimizing local order, then use sort
3. local interactions to construct full sequence &rArr; DP
4. if direct greedy is too hard, we can consider the forcing moves that we need to do, before doing greedy
5. we can also try writing partial brute force and see if there are redundant calculations (4, 5 example: D9 ZR contest 2026 T3/D)
6. if problem only needs floating point, we can consider using taylor series or some other numerical method to find the answer.
7. if a problem is concerned with range counting, we try to split the range and hang the answer calculation on the split points. we need the split points to make the answer calculation "easier" and there can only be a limited amount of them.
8. first consider how we can check if a state is valid, then we count them
9. layering, convert to 0/1 problem: $$\text{ANS} = \sum_{B}^{\infty}{f([a_i \ge B])}$$
10. Factorization &rArr; (maybe) Sqrt Decomposition
11. If a dp is hard to compute, try with a different angle and different set of decision points.
12. Only keep the dfs tree of a graph when trying to solve some types of graph theory problems. Then we can track only 2 type of connections: cross edges and tree edges.
13. Difference $\le 1$ &rArr; (maybe) Eulerian Path / Circuit.
14. If there is is a $\frac{1}{k}$ in the minimum expression, we can try to construct $k$ methods that sum to $tot$ and pick the minimum. This is for construction
15. $\mathbb{E}[\min(x)]$ &rArr; (maybe) tail sum.
16. $\mathbb{E}[\max(x)]$ &rArr; (maybe) Min-Max (PIE).
17. If we want to count permutations (keep track of which values has been picked like in bitmask DP), we can also consider subset inversion to optimize it.
18. $\mathcal{O}(n^2)$ dp like $f[i] = \sum_{\text{condition}}{f[j]}$ may be optimized with D&C.
19. If there are 2 variable values in the answer, or that there is a very difficult constraint that is hard to work with, we can simply iterate over it and try to solve the leftover. (treat it as a constant)
20. When calculating path length sums on tree, we can use edge contribution ($w[e] \cdot sz[u] \cdot (n - sz[u])$)
21. We can add in values incrementally.
22. REDUCE MEAN VALUE!!! (I'M THE OPPOSITE OF ARTIFICIAL INTELLIGENCE!!!)
23. When having no idea what the answer is, we can set everything as a variable and check if they have any relationships (see CF1764G D9)
24. First construct extremum then adjust.
25. When optimization is difficult, try changing the order of summation.
26. Try to think of individual contribution rather than full sequence contribution (especially when the contribution is symmetrical)

