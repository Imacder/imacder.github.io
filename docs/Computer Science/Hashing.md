## Normal Hash

### String Hash

**DO NOT USE $2^{64}$ AS MODULUS!!!**
It's otherwise quite simple.

### Sum Hash

We can assign a different random value for each element. The hash of a set is its sum. This can support set operations on the fly, but only works for multisets.
(P.S. Xor hashing is dangerous, it doesn't support set ops and doesn't support multiset.)

We can also estimate the set size with this type of hash. $E = \frac{2H}{M}$, where $M$ is the max generated number. (Though we can't use a modulus for this.)

## Atypical Hash (Sketches)

## Min Hash

We can assign a different random value for each element. The hash of a set is its minimum. The main use case is find the Jaccard similarity, $P(H_a=H_b) = \frac{a \cap b}{a \cup b}$. This type of hashing can also record the size of a set (unique elements), $\mathbb{E}[H] = \frac{1}{1+k}$.

### Hyper Log Log

I have no interest to expound on this here. [This](https://en.wikipedia.org/wiki/HyperLogLog) is the algorithm. It is used to preserve cardinality information for set union. For intersection, we need to use inclusion-exclusion, and we can't preserve the set, only find the number.

### Theta Sketch

The ultimate set operation hash.