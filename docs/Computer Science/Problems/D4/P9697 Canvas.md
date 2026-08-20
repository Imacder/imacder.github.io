## Step 1

We can first recursively delete any node that has only 1 assign operation. These doesn't effect the problem.

## Step 2

Out of all the $(1,2)$ operations, we can build a graph with directed edges $(u \rightarrow v)$ where we assign $u$ to $1$ and $v$ to $2$. The assignment process is difficult to process forward, so we can process it backwards, each time we reach a new vertex we won't change it. The process is the same as choosing a set of starting vertices and letting it fill the graph.

We can find the SCCs of the graph and count the number of sources in the resulting DAG. There are exactly these many vertices that will be assigned $1$, everything else will be $2$.