## Undirected Version

For a undirected graph $G$, we construct:

- **The Adjacency Matrix ($A$):** This is an $n \times n$ grid that tracks which vertices are connected. If vertex $i$ and vertex $j$ are connected, the entry is $1$. If not, it's $0$. The diagonal is always $0$.
- **The Degree Matrix ($D$):** This is an $n \times n$ matrix where the diagonal entries show the "degree" of each vertex (how many edges connect to it). Everywhere else is $0$.
- **The Laplacian Matrix ($L$):** This is the star of the show. You find it by subtracting the Adjacency matrix from the Degree matrix: $$L = D - A$$
We delete a single row and column at vertex $r$ (the root), and calculate $\det(L)$, which yields the number of all possible spanning trees (rooted at $r$, but roots doesn't matter for undirected graphs.)

## Directed Version

We replace $D$ with in-degree for Out-Trees, and out-degree for In-Trees (they are reversed.) Now the roots does matter.

## Extension

If we want to calculate the number of $n$ trees with roots $r[1 \dots n]$, then we delete all the rows and columns for every $r_i$.