## Boruvka

We start with all nodes disjoint. In each round, we add the the minimal edge for each connected component. Each time the number of component is cut by half.

## Kruskal Reconstruction Tree

Instead of directly merging the DSU, we can add a new node and let the original connected subtrees point to this new node.

This idea is useful for maintaining the roll back versions of the merging process.

## 朱刘 (For Directed MST)

0. We need to ensure the graph is a SCC.
1. Repeat the following:
	1. Find the minimum weighted incoming edge to every node.
	2. Check if the edges chosen contains loops:
		1. Yes. Then reduce the cycle into a super node. Replace the incoming edge weight to a node $u$ in a cycle with its weight minus the cycle edge to $u$.
		2. No. Break the loop.
2. We expand the super nodes, removing the edge before the attachment node of all cycles.

To implement this efficiently, we use a DSU to maintain the super nodes, and use a mergeable heap to maintain the minimum incoming values. We also need a global offset / lazy for the heap.

We first do the contracting part by first iterating over every node (including the added super nodes, we can do it sort of like DFS.) We first try to add the smallest incoming edge to $u$ (call it $v$). If $v$ has not been visited, simply add it in and DFS $v$. Otherwise there is a cycle, we contract it, building a sort of merging tree timeline like Kruskal Reconstruction Tree. Then we basically roll back everything using the tree to obtain the answer.