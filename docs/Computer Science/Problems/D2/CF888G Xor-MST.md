## Step 1

I think Prim's algorithm will fair better for this specific problem.
Say we have found the set $U$, with a set of minimum outgoing edges for each of $U$. When we add a node in we have to invalidate some of the edges. So, no.

## Step 2

Consider Kruskal. recursively build for left and right, then connect them.