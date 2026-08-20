## Basics

Independence of subset cannot show independence of union. See [here](https://share.gemini.google/SgCQV7jHegln).

## Posterior Probability

Let $P(B|A)$ denote the probability of $B$ given $A$ has occurred.
$$P(B|A) = \frac{P(AB)}{P(A)}$$
Or equivalently:
$$P(AB) = P(B|A)P(A) = P(A|B)P(B)$$
We are essentially rescaling the scale to $A$. Let $\bigcup{A_i} = \Omega$, where $\Omega$ is the set of all possible situations, and all $A_i$ are independent. Then:
$$P(B) = \sum{P(A_i)P(B|A_i)}$$
The intersection is dropped in $P(B)$ because $P(B \cap \Omega) = P(B)$. After a bit of derivation, we can get to Bayes Theorem:
$$P(A_i|B) = \frac{P(A_i B)}{P(B)} = \frac{P(A_i)P(B|A_i)}{\sum{P(A_i)P(B|A_i)}}$$

## Expectation

The following hold for any $x$ (not necessarily independent.)
$$\mathbb{E}\left[\sum{x_i}\right] = \sum{\mathbb{E}[x_i]}$$
Product needs to be independent:
$$\mathbb{E}\left[\prod{x_i}\right] = \prod{\mathbb{E}[x_i]}$$
There is a similar expression for Posterior Expectation.
$$\mathbb{E}[B|A] = \sum{B \cdot P(B|A)}$$
Therefore:
$$E[B] = \sum{\mathbb{E}[B|A_i] P(A_i)}$$
(Same definition of $A$ as above.)

This is a useful trick for calculating $\mathbb{E}[\min(x)]$. We introduce the tail sum formula:
$$\mathbb{E}[x] = \sum_{k=0}^{\infty}{P(x>k)}$$
The variable ranges from $0$ to $+\infty$. This is also true for continuous variables. The intuition is that when we build $\mathbb{E}(x) = \sum_{k=0}^{\infty}{k \cdot P(x = k)}$, we are building vertically. Here we switch to horizontal calculation, for each $x$ the contribution comes from what's above it.

The fascinating part about this transformation is that we essentially turned a $\min$ problem to a greater-than-for-all problem.