## Trie

### Property 1

Every node on the trie represents $\{S | S \text{ is one of the given string's prefix}\}$.

### Property 2

It's a tree.
You can do tree operations like segment tree merges, persistence, DP and etc.

### Property 3

0/1 Trie can be used for finding the kth smallest / largest xor sum.

#### First k

#### Sum / Xor-sum

## Palindromes

### Manacher

We always store a maximal extension $[L, R]$ for all previous $i$. (By maximal, I mean  the $R$ is the maximum). We just check the portion covered by the maximal extension for the current $i$, then we brute force to try to extend it further. Because $R$ only goes forward, the complexity is $O(n)$.

There is also another type of extension: we don't move forward for $R$, we first set the range to be the reflection of the range of $i$'s reflection, then we move back to $R$. This is also $O(n)$.

### PAM

This is basically the palindrome version of KMP. We maintain a fail array that represents the length of the longest border palindrome. To calculate the fail we simply extend it like in KMP. If we can't extend, we do $l = \text{fail}[l]$.

This can also allow us to calculate the number of different palindrome for a sequence. We can build 2 trees, one for even palindromes and one for odd, then we can build an automaton.

Because of the symmetry of a palindrome, we can insert characters both in the front in at the end.

## Border

### Periods

If the length of border of $s$ (call it $l$) satisfies $2l \ge n$, then $n - l$ is a period of $s$.

It easily follows that all borders with $2l \ge n$ forms an arithmetic progression with difference of the smallest period of $s$.

### The Main Result of Border Theory

By what's derived above, we have the following:
If we sort all the lengths of all the borders of $s$ in ascending order, they will be divided into $O(\log n)$ arithmetic progressions.

## SAM

See [SAM](SAM.md).