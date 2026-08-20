## What is DP

Each DP state is a node on a graph $G$. Each transition is a **directed** edge on the graph. Typically $G$ is a DAG. We iterate through the DAG to the end points, and these are the answer.

## DP on DP

Sometimes we need to record a complex object for the state. When we do vanilla bitmask DP, the number of states explode. However, there is a large portion of these bitmask states that are invalid.

We can push state compression to its limits. We assign each node / state in the DAG an id by running a (partly) brute force search to get all the states. Now we've built the DAG, and we can run the normal DP on the DAG to obtain the answer.

Two steps on how to solve this type of DP:
1. Figure out how to check if a given state if valid (answer to the subproblem)
2. Figure out how to use the check to construct solution

The checker is an Automata.

## Monotonic Decision Point

#### Binary Search on Queue

**TBD**

#### Alien's Trick

If $g(s)$ is convex where $s$ is the number of items that had to be chosen, then we can add a penalty $ks$ to the $g(s)$. By controlling $k$, we can change the optimal $s$, and we can binary search.

## DDP

use matrix multiplication for dp on a path on tree

