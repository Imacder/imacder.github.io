## Network Flow

### Max Flow (Dinic)

#### Basics

We can think of a positive flow $u \rightarrow v$ as a negative flow $v \rightarrow u$. The same idea applies for the capacity of an edge (i.e. $[l=-f, r=c-f](u \rightarrow v) \iff [l=f-c, r=f](v \rightarrow u)$). This allows to reverse push flow through an edge to cancel out what had been pushed.

#### Ford-Fulkerson (Naïve Approach)

We can repeatedly search for an augmenting path (path with all positive $r_e$), then push the maximum flow through it (we also need to push negative flow through its reverse edge). If no such edge exists, then break the loop.

#### Dinic

We find the naïve approach is way too slow. Dinic still repeatedly searches for augmenting paths, but it does so in batches. $\mathcal{O}(n^2 m)$.
##### Phase 1 BFS

We build a depth for all nodes with all the $r_e > 0$ edges. This helps direct the second phase

##### Phase 2 DFS

We search for the Block Flow. DFS takes the bottleneck upstream as input and returns bottleneck for entire path from downstream. At each $u$, it iterates over all the edges and keeps track of which edge it had tapped out. After recursing to its child it updates the edge with the bottleneck (and it's inverse edge) and sums up the flows downstream for output.

#### Bonus: Edmonds-Karp

In this version, we push the flow through one at a time, but we only push the shortest path in BFS through. $\mathcal{O}(nm^2)$.

### Min Cost Max Flow (SSP)

We priorities maximizing flow, then minimizing cost.

Similar idea to EK, except we search for the shorted path with the cost weights instead of a simple BFS. We keep the flow part unchanged, and accumulate answer with the cost.

The only part different from Dinic / EK is the distance (calculated by BFS or SPFA or Dijkstra). Because we use the shortest path every time, we also add the minimum cost in every round, thus obtaining a optimal result.

#### Primal Dual

SSP uses SPFA, which is very slow. We can use the idea from Johnson's algorithm. 

We can first run a slow SPFA to generate a potential $h$. We set the edge cost/weight that we use to run Dijkstra to $w'(u \rightarrow v) = w(u \rightarrow v) + h[u] - h[v]$. After each augmentation, we can simply do $h[u] \leftarrow h[u] + d[u]$ where $d[u]$ is the raw distance (no correction for potential) calculated by Dijkstra on the last round. $\mathcal{O}(F m \log n)$, where $F$ is the max flow.

[Proof](https://share.gemini.google/cP1t6IFEK0yu) of why $h[u] \leftarrow h[u] + d[u]$ works. The conversation includes Max Flow and Min Cost Max Flow.

### Min path cover on DAG

We split each node on the original graph into a left and right part. For original edge $u \rightarrow v$, we turn it into $u_L \rightarrow v_R$.

Ans = $|V_{\text{original}}|$ - Max Matching

[Intuitive Explanation](https://share.gemini.google/0kd6k5GbQpH7). Essentially you start with everything connected, and add in edges. $$\max(d^+{u}), \max(d^-{u}) \le 1 \iff \forall u_L,u_R \text{ has only 1 edge connected to it}$$
### Min Cut

Ans = Max Flow

#### Special Case on Planar Graphs

Ans = Shortest Path on Dual Graph

### Bipartite Graphs

#### Max Matching

##### Hall's Theorem

Given a bipartite graph $G = (X, Y)$, the max matching (of $G$, but this also the max chosen elements in $X$ and $Y$) is:
$$|M^*| = |X| - \max_{S \subseteq X}(|S| - N(S))$$
where $N(S)$ is the number of neighbors of $S$ and $\max_{S \subseteq X}(|S| - N(S))$ is $S$'s defect.

Note that when $S = \emptyset$, the theorem reduces to the original. In special cases where you do not need the actual matching, using the deficiency is actually easier and faster to calculate just the matching count.

#### Min Vertex Cover

Ans = Max Matching

#### Min Edge Cover

Ans = $|V|$ - Max Matching

#### Max Independent Set

Ans = $|V|$ - Max Matching

### Recessive Flow

(**TBD**)

## Connectivity

### Dynamic SCC

Divide and Conquer.
(**TO BE CLARIFIED**)

### 2-SAT

#### Optimizations

##### At most 1

When we constrain only one of a set can be true, we can take it's prefix sum. If the sum of the current value is already $1$, then everything after will be $1$. 

**Rule A: If a variable is true, its prefix is true.**
$$x_i \implies p_i$$

**Rule B: If a previous prefix is true, the current prefix is true.**
$$p_{i-1} \implies p_i$$

**Rule C: The "At-Most-One" constraint.** If a previous prefix is true (meaning one of the earlier elements was 1), the current element _must_ be false.
$$p_{i-1} \implies \lnot x_i$$

##### Exactly 1

NP-Complete.

## Eulerian Paths & Circuits

### BEST Theorem

#### Lemma

When we take the last edge DFS takes to leave a node. This forms a tree.

Each tree, along with all the orders of edges exits (except for the last) uniquely identify a circuit.
##### Theorem

Multiply Matrix Tree and the permutation count together and you'll get the number of Eulerian Circuits on a **DIRECTED** graph.

## Spanning Tree

See [spanning tree](Spanning%20Tree).

## Misc.

### Minimum Cycle

We can characterize each cycle by the largest indexed node inside it. This characterization connects very well with Floyd's Algorithm. Before iterating the $k$th node, we can first compute the cycle (because the distance is not yet contaminated with $k$ information yet.)

### 3-cycle counting

For a undirected graph we assign a direction to each edge pointing from low degree to high degree. It is guaranteed that the outdegree for any node is at most $\sqrt{2m}$. 

We can iterate over all $u$, then iterate over all $u \rightarrow v$, then iterate over $v \rightarrow w$. We simply check if $u \rightarrow w$ exists.

The complexity is correct because we are basically iterating over all the edges  ($\mathcal{O}(m)$) in the first loop, and the second loop only runs $\mathcal{O}(\sqrt{m})$ times. Combined this is $\mathcal{O}(m^{1.5})$.

#### Extension: 4-cycle

We still assign the edges directions, but we flip their directions (high to low this time) (actually we can also do this in 3-cycle, but the time complexity proof is messier).

With calculate the answer of cycle on its max order node $a$. We can iterate over $a \xrightarrow{\text{directed}} b \xrightarrow{\text{undirected}} c$. The second iteration is undirected because $b$'s order can be smaller than $c$'s, however we do need to throw out any invalid (order larger than $a$) $c$. We can simply use an auxiliary $\text{cnt}$ to track how many paths like this we have already counted and accumulate the answer.

[Proof](https://share.gemini.google/KTKKaaH9i9ko) of complexity.