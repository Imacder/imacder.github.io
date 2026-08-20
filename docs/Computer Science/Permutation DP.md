## Insertion

We track the state to be $f[i,\dots]$ to be the number of permutations when I have inserted $1 \dots i$ into the permutation. We essentially just dropped the bitmask, but usually we need some other metric to store the information.

In this case, most positional information is lost. We can restore some relative positioning (if it's consecutive or not) with the method in Example 2.
### Example 1 (Luogu P6323)

#### Statement

Count the number of permutations that have exactly $k$ inversions.
 
 >[!example]- Solution
> We can trivially construct the dp state to be $f[i,k]$, where $i$ is $1 \dots i$ in the permutation, and $k$ is the number of inversions created.
> We actually don't have to store anything else for the count, because each time we insert an element, it's guaranteed to be the largest. 
> $$\Delta \text{inversions} = \text{\# of inserted positions after it}$$
> Then, we can just iterate where $i$ is inserted into.
> $$f[i,k] = \sum_{j=0}^{i-1}{f[i-1,k-j]}$$

### Example 2 (Luogu P5999)

#### Statement

Find number of permutations such that $(\pi_i - \pi_{i-1})(\pi_i - \pi_{i+1}) > 0$ ($\pi_0 = s ,\, \pi_n = t$). 

>[!warning]- Issue
>If we try to only use $i$ for permutation state, we cannot check if it connects with a contiguous segment. And therefore, if $i$ attaches to contiguous segment(s), we cannot check if the elements inside forms a monotonic subsequence.

>[!example]- Solution
>If only contiguous segments break the math, then we can just add a contiguous segment count $j$ to the dp state. There are three types of insertions:
>1. Start a new segment: $f[i,j] = f[i-1,j-1] \cdot j$
>2. Attach to a old segment: $f[i,j] = 2 \cdot f[i-1,j] \cdot j$
>3. Connect 2 old segments: $f[i,j] = f[i-1,j+1] \cdot j$
>
>However, 2 is invalid for this problem setup. If we attach, the side we attaches to is smaller than $i$, and later there will be some other $i'>i$ that connects to $i$ from 2 or 3, this violates the problem statement.
>We can just do 1 & 3, and treat $s$ and $t$ individually to solve the problem.

#### Example 2.1

ABC468 G. Literally the same idea. (P.S. I wrote example 2 4hrs before doing the contest and I passed G)

## Bipartite Matching

We track how many numbers we've considered / what position have we iterated to $i$. These two are the same, so we introduce 1 new position and 1 new number at the same time. We track how many of these positions are left empty / how many numbers I need to pair with some later position. Final dp state looks like $f[i,j,\dots]$.

In this state setup, we gain 1-1 positioning information, but we cannot distinguish between any previous empty positions, we only know they are there.

**TBD**