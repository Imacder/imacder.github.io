## DS

## Tricks

### Small to Large Merging

This guarantees $\mathcal{O}(n \log n)$ complexity.

### Segment Tree

#### Merge

When merging segment trees, the amortized complexity is always kept if you don't create new nodes. (This rules out persistence, and we also need careful handling of lazy tags.)

If it is persistent, then use small to large merging. (Or if the sets we are merging are disjoint, we can actually )

## Graph Theory

### Tree

#### Diameter Merge

The diameter of the merged tree of 2 tree is the the maximum distance between all pairs of endpoints of the original 2 diameters.

The weighted diameter:
$$D(u,v) = w(u) + w(v) + \text{dist}(u,v)$$
Also has this property.

### Spanning Tree

If $T_1$ and $T_2$ are two different spanning trees of the same graph, they obey the **Basis Exchange Theorem**:
- For any edge $e$ that is in $T_1$ but not in $T_2$, there is always some edge $f$ that is in $T_2$ but not in $T_1$ such that swapping them—specifically $(T_1 \setminus \{e\}) \cup \{f\}$—results in a valid, new spanning tree.

### Connectivity

When we reduce the EBCCs or VBCCs, they both form trees.

## Misc.

### Xor Basis

The span of sequence $a$'s difference is equal to the span of $a$.

### GCD

GCD of sequence is equal to GCD of its difference.