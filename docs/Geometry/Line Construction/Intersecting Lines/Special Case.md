# Special Case (sA-type)

This is the A-type, but $A$ and $D$ are the same.

[//]: # (TODO: add figure)

## Basic Usage

Just use the [properties](Basic%20Structure.md#properties) like normal.

The only special thing is that this gives squares instead of just products.

$$ OA ^ 2 = OB \cdot OD $$

### Examples

1. 《核心考点·中考数学》P21 03 04
2. 《核心考点·中考数学》P41 (HARD)

## Transformations

### Apollonius Circle

Discussed in [Circles](../../Circles/Basic%20Structures.md#fixed-ratio-fixed-length).

### Inversion

#### Definition

Given a point $P$, the center of inversion $O$, and the radius of inversion $r$.

The inverted point $P'$ is on ray $\overset{\Large\rightarrow}{OP}$, and $OP \cdot OP' = r^2$.

#### Properties and Derivation

<iframe src="https://www.geogebra.org/calculator/jwm9xyet?embed" width="1200" height="700" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

The inversion of a circle is another circle. Here lines are considered circles of $r = \infty$.

Derivation:

1. Construct the diameter ($MN$) of $\odot A$ that goes through $O$ &rArr; $\angle MPN = 90^\circ$
2. Construct the inversion ($M'N'$) of $MN$
   &rArr; $\triangle OPM \sim \triangle OM'P' ,\, \triangle OPN \sim \triangle ON'P'$
3. $\angle M'P'N' = 90^\circ$ &rArr; $P'$ is on a circle with diameter $M'N'$

#### Usage

[//]: # (temp message: transform the denominator to a fixed segment, connection to circles)
1. Used to solve ratio extremum (R_n)
2. Find locus (usually the $OP \cdot OP' = r^2$ is derived)

### Transformation 3

I've found no other mention of this type anywhere, thus the crude name.

[//]: # (TODO: add figure)

#### Construction

1. $P$ is on line $l$, $A ,\, B$ are fixed endpoints.
2. $\triangle PAB \sim \triangle PBQ$, where $Q$ is on $AP$

#### Derivation

1. Construct the reflection of $B$ ($B'$) about $l$.
2. $B'P^2 = BP^2 = PQ \cdot PA$, hence $\triangle PAB' \sim \triangle PB'Q$.
3. $\frac{B'Q}{B'A} = \frac{B'P}{AP} = \frac{BP}{AP} = \frac{BQ}{BA}$.
4. $\frac{BQ}{B'Q} = \frac{BA}{B'A} = \text{const.}$ &rArr; Apollonius Circle

#### Explanation

Currently, I'm unable to think of an explanation not containing some guesswork.

The main thing to notice here is that $A$ is on $Q$'s locus (when $AP = BP$). We can immediately see that the locus
isn't a line (so it's a circle). 

Since there is NO fixed angles here, if we want to go forward with this method, we need to construct our own.
Try with $BH \perp l$, this will characterize l with the distance from $B$ to $l$, and give use a fixed angle.
However, this construction doesn't work because unlike in inversion, the relationship given here cannot give us
another triangle (containing $Q$ as the $90^\circ$ vertex) similar to $\triangle BHP$.

Try with Apollonius Circle. There are only two fixed points $A$ and $B$, $A$ is on the locus, therefore we can guess
that $B$ is one of the endpoints. That gives us some fixpoint $B'$ s.t. $\frac{BQ}{B'Q} = \frac{BA}{B'A}$. When we rearrange
the equation, we can see the similarity ratio of $\triangle PAB \sim \triangle PBQ$, so we can construct the same for $B'$.
That actually allows use to backtrack to $B'P = BP$, and since $B'$ needs to be fixed, $B$ and $B'$ are mirrored about $l$.

With this thought process, we can also see why $P$ **has to be** on a line. When $P$ is on a circle, we can still construct
$B'$ with Apollonius Circle. But $B'P \neq BP$, going against "backtrack to $B'P = BP$", therefore the locus is some much more
complex 4th order thing.

### Further Reading

Another non-linear transformation is [Rolling Similarity](../../Rotation/Rolling%20Similarity.md).

<script>
  window.MathJax = {
    tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
  };
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>