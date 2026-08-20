We have 2 edges sets $E_1$ and $E_2$. We want to find $E_1 \cup E_2'$ where $E_2' \subseteq E_2$, such that there exists an Eulerian Circuit in the graph formed. ($E_1$ can already connect the entire graph.)

We basically need the degree to be even for every vertex. 

We can build a spanning forest for $E_2$. For each vertex we can calculate whether it needs to change its parity (based on the graph built with $E_1$). 

Let's only consider the case for 1 connected component, because we can't change their parity anyway. Therefore, the number of (originally) odd vertices must be even (we can only reduce the number of odd vertices by 2). Now we only need to drag up (a) subtree(s) from the tree that connects all the odd vertices and have no odd degree edges itself. This can always be done, because we can drag up any paths that connects them and xor the path usage.

We can do a post order traversal of the spanning tree. If the current node is odd, we can try to pair it up with one of its children. If 2 children are odd, we can pair them up. If there is still an odd one (the current node) we pass it on to its father.