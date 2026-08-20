## Example String

We'll use $s = \text{"abcbc"}$ and $s = \text{"cocoa"}$ as examples. We'll use 1-based indexing.

## Example Problem

Given a string $s$, find occurrences of $t$ in $O(|t|)$ time.

## Definitions

### States $u$

Each $u$ represents a set of substrings of $s$ whose set of occurrences' endpoints are the same (equivalent class).

For the substring "bc", it occurs at positions $\{[2,3], [4,5]\}$. We ignore the left side bound (because we want the set of all matches of the entire target string in $s$, and storing the end positions are enough.) Let's write the end positions of a string $t$ as $\text{endpos}(t)$. In this case, we have $\text{endpos}(\text{"bc"}) = \{3,5\}$.

Over all $O(n^2)$ possible substrings of $s$, there are 2 distinct (distinct iff two string have the same characters in the same positions) strings with $\text{endpos}(t) = \{3,5\}$, namely "bc" and "c". These 2 strings go into the same state $u$. (Actually I think it's better if we use the endpos to represent a state, in this case $\text{endpos}(u) = \{3,5\}$.)

Also, let's denote:
1. The substring set at $u$: $S(u)$.
2. The maximum length of all strings in $S(u)$: $\text{len}(u)$
3. The minimum length of all strings in $S(u)$: $\text{minlen(u)}$
Recording the max and min lengths are enough because all strings in $S(u)$ form a continuous length range of suffixes at $\text{endpos}$.

If $|s| \in \text{endpos}(u)$, then $u$ is a terminal state. The state of the empty string (or $\text{endpos}(u) = [0, |s|]$) is the initial state $u_0$.
## Transitions

### Forward Transitions

For a state $u$ with transition edge $c$:

>1. For each $i$ in $\text{endpos}(u)$, we check if $s[i + 1] = c$. If so we add it to $\text{endpos}'$.
>2. We find state $v$ with $\text{endpos}(v) = \text{endpos}'$ (exactly the same), this is the transition (denote: $\text{nxt}(u,c)=v$)

This is a filtering process: whenever you process a new character, you remove the impossible $\text{endpos}$ and you have the new state.

Notice that when we run a substring $t$ of $s$ through, it traces a path through each of its characters until it finally ends up in its equivalent class. Now we have a formal construction of SAM (except the suffix links):

>For each of $s$'s suffixes $t$, we iterate through its characters, performing the algorithm above. If we didn't find $v$, we simply add a state $v$ with that exact endpos.

Now, by definition, each path of every substring of $s$ has been traced (because we iterated through all suffixes, and the prefix of suffix is a substring), and now ends up in a filtered equivalent class of $\text{endpos}$. Also, for any non-substring of $s$, by the time it traced through it's max prefix to substring match, it will end up in a position where no state transition is created for the new character, so we can know it's not a valid substring.

### Suffix Links

When we encounter a position where we can find no further transitions, we must need suffix links. This is similar to $\text{fail}$ for AC automaton.

We can find state $v$ with the smallest $\text{endpos}$ that is a superset of $\text{endpos}(u)$. The suffix link of $u$ is $v$. (denote: $\text{link}(u) = v$) When we follow this suffix link (after we can't find a transition for $u$), the length of match is automatically longer than $\text{link}(u)$, so we can set it to $\text{len}(\text{link}(u))$. 

The suffix links form a tree, which is also the suffix tree of $\text{reverse}(s)$. This is because $\text{endpos}(u) \subset \text{endpos}(v)$ iff every / any element of $S(v)$ is the suffix of every / any element of $S(u)$ ("any" or "every" doesn't matter, the condition hold regardless.) And since endpos form prefixes, it's a suffix tree.

The suffix links (and the tree it forms, let's just call it the suffix link tree) has many useful properties, and is extremely useful. Common usages include DP and fail jumping.

## Construction

We can construct the SAM in $O(n)$ by adding the character in $s$ one at a time sequentially.

### Variables to track

1. $\text{len}(u)$
2. $\text{link}(u)$
3. $\text{nxt}(u,c)$
4. $\text{cnt}$ (the number of states we have in the automaton right now)
5. $\text{last}$ (the state $u$ with $\text{endpos}(u) = \{|s|\}$, the ultimate terminal state)
Note that we don't track $\text{endpos}$ and terminal states but instead construct it afterwards if needed.

### Algorithm

1. Initialize SAM with $\text{cnt} = 1$, $\text{last} = 1$, and the initial state $u_0$ with $\text{len}(u_0) = 0$, $\text{link}(u_0) = \text{null}$, and no $\text{nxt}$.
2. Iterate over $s[i] = c$.
	1. Create a new last state $\text{cur}$ with $\text{len}(\text{cur}) = \text{len}(\text{last}) + 1$ and no $\text{nxt}$.
	2. Iterate $p = \text{last}$ back with $p = \text{link}(p)$, setting $\text{nxt}(p, c) = \text{cur}$, until $p = \text{null}$ or $\text{nxt}(p, c) \neq \text{null}$. This is basically iterating over all suffixes of $\text{last}$ and extending it.
	3. There are 3 cases, (denote $q = \text{nxt}(p, c)$ if it exists):
		1. $p = \text{null}$: $c$ has never appeared before, $\text{link}(\text{cur}) = u_0$.
		2. $\text{len}(p) + 1 = \text{len}(q)$: $\text{link}(\text{cur}) = q$
		3. otherwise: We create an intermediate state $w$ with $\text{len}(w) = \text{len}(p) + 1$ and the same $\text{link}$ and $\text{nxt}$ as $q$. We point everything that had been pointing to $q$ to $w$ by traversing the suffix links from $p$, suffixes longer than $p$ doesn't have to change their transitions. Finally, set $\text{link}(\text{cur}) = \text{link}(q) = w$.

### How does it work

We first observe what is the SAM like before adding the character $c$.

There will be a chain from $\text{last}$ to $u_0$ following the suffix links, they are $p_0 = \text{last}$, $p_1 = \text{link}(p_0)$, …, $p_n = u_0$. From point $k$ onwards, $q_i = \text{nxt}(p_i,c), i \ge k$ always exists. This is because the strings in $S(p_i)$ get progressively shorter. All $q_i$ also lies on a suffix link chain, because they are $S(p_i) + c$ and thus form a continuous suffix chain.

There are 2 things we notice:
1. The incoming $c$ transition to every $q$ except the first (from bottom) is from $p$.
2. Let the first $p$ that has a transition $c$ be $P$ and its corresponding $q$ be $Q$. All transitions $c$ to $Q$ from a state longer than $P$ must have $P$ as an ancestor. All shorter must be one of $P$'s ancestors already on the $p$ chain.

>[!proof]- Proof of the 1st Observation
>All $q$ after $Q$ is a suffix $Q$. This means $S(q)$ is strictly shorter than $S(Q)$. The minimum length string in $S(Q)$ is a suffix of $S(P)+c$, therefore all $S(q)$ is a suffix of $S(P)+c$. To put it simply:
>$$S(q) \xrightarrow{\text{is suffix of}} \min(S(Q)) \xrightarrow{\text{is suffix of}} S(Q) \xrightarrow{\text{includes}} S(P)+c$$
>Let's remove the last character from $S(q)$, then they are suffixes of $S(P)$. Since all suffixes of $S(P)$ live on $P$'s suffix link all the way to $u_0$, every incoming transition $c$ to $q$ is from $p$.

>[!proof]- Proof of the 2nd Observation
>$S(Q)$ forms a contiguous range of suffixes. Let some $S(r) + c \subset S(Q)$ be longer than $S(P) + c$, then $S(P)$ is a suffix of $S(r)$ (after removing $c$). Therefore $P$ lives on the suffix link of $r$ from $r$ to $u_0$.

$Q$ is the first state that represents a suffix of the entire string after adding $c$. When we try to add set $\text{link}(\text{cur}) = Q$, we are essentially trying to add a new endpos to all of $q$. This would work for all $p$ after $P$, because they are $P$'s suffixes. But this wouldn't work for all $p'$ longer than $P$ that have transition $c$ to $Q$. This is because by definition, $P$ is the longest state that is a suffix of $s$ and has transition $c$, any state longer than it wouldn't be a suffix of $s$ and couldn't transition to a state with endpos containing the last character. It follows that $\text{len}(Q) = \max(\text{len}(p')) + 1$.

When we check $\text{len}(P) + 1 = \text{len}(Q)$, we are asking if such a $p'$ exists. If so, then there are a portion of $Q$'s incoming states that wouldn't take the new endpos. Therefore we need to split the original $Q$ into 2 states, one that can add a new endpos, and one that couldn't. If no such $p'$ exists, then everything that transitions to $Q$ is a suffix of $P$, and they would happily accept the new endpos. Therefore there is no need to clone.

See [here](https://cp-algorithms.com/string/suffix-automaton.html#linear-number-of-operations) proof of linear complexity.

