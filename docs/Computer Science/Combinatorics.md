## Inclusion-Exclusion Principle

I don't know how I can pass a single problem without this.

### Some Basic Formulas

(1)
$$\binom{a}{b}\binom{b}{c} = \binom{a}{c}\binom{a-c}{b-c}$$ (2)
$$[n = 0] = \sum_{0 \le i \le n}{\binom{n}{i}(-1)^i}$$
### Binomial Transform

$$f(n) = \sum_{i=0}^n{(-1)^i\binom{n}{i}g(i)} \iff g(n) = \sum_{i=0}^n{(-1)^i\binom{n}{i}f(i)}$$
$$f(n) = \sum_{i=n}^M{(-1)^i\binom{i}{n}g(i)} \iff g(n) = \sum_{i=n}^M{(-1)^i\binom{i}{n}f(i)}$$
We can also combine the $(-1)^i$ into $g(i)$

We can define $f(k)$ to be the number of cases such that at least $k$ conditions are satisfied (the rest can be anything, and the conditions have to be symmetric), $g(k)$ to be the number of cases with exactly $k$ conditions satisfied.

There is a simple relationship from $g$ to $f$:
$$f(n) = \sum_{i=0}^n{\binom{n}{i}g(i)}$$
Then we can use its inverse to find $g$.

### Subset Inversion

$$g(S) = \sum_{T \subseteq S}{f(T)} \iff f(S) = \sum_{T \subseteq S}{(-1)^{|S|-|T|} g(T)}$$
### Min-Max

$$\max(S) = \sum_{T \subseteq S} (-1)^{|T| - 1} \min(T)$$
This can be derived with (2). The $[n = 0]$ can be seen as selection. There is a general form.

$$\max_k(S) = \sum_{\substack{T \subseteq S \\ |T| \ge k}} (-1)^{|T| - k} \binom{|T| - 1}{k - 1} \min(T)$$

Common use case: The expectation of the time point where every element has appeared. Usually "at least 1" is easier than "all".

### Tree?

For each connected component on a tree, the following holds:
$$|V|-|E| = 1$$
Therefore to count the number of connected components, we can find the valid $V_i$ and $E_i$.
$$\text{cnt} = \sum{|V_i|} - \sum{|E_i|}$$
Or better, for each $u$/$e$, we can find the number of $V$/$E$ that contains it.

### Distinct Elements

#### Problem Setup

There are $n$ variables $a_i \in S_i$, and we want to find the number of choices of $a$ such that $\forall i \neq j, a_i \neq a_j$.

#### Intuition

The "not equal" condition is hard to track, so we track $a_i = a_j$ instead. We also notice that this condition has transitivity.

The brilliant idea is to build a graph on $[1 \dots n]$ where there is an edge when $a_i = a_j$.

#### Solution

See [here](obsidian://open?vault=Imacder_Notes&file=Slides%2Fmain%20(1).pdf). (互不相等容斥) **TO BE CLARIFIED.**