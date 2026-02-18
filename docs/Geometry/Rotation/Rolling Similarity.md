# Rolling Similarity

Note: This is more like and example problem rather than a typical structure.

## Problem

[//]: # (TODO: add figure)

Given a fixed segment $AB$, a fixed point $C$, and a point $P$ moving along a line (or circle, just ensure that
after an inversion transformation, its path is still simple). Rotate $\triangle ABP$ to $\triangle CQP$ (i.e 
$\triangle ABP \sim \triangle CQP$.) Find the locus of $Q$.

## A Reduced Problem

[//]: # (TODO: add figure)

Let first look at the case where $C$ and $B$ are the same. We'll try to find some fixed point with some
product relationship with $P$ and $Q$.

This is a rotational similarity with collinear side. After enumerating the properties of this similarity, we find that
there is obviously no fixpoint besides $A$ and $B$. The products concerning $A$ and $B$ aren't useful, so we can try to construct.

Let the similarity ratio be $k$. We find that everything besides $AB$ and $AP$ have a coefficient of $k^n$, therefore
we need to reduce the order of $k$. We can notice that $PQ$ is one order higher than $BQ$, so we can try dividing $BQ$ by
their ratio again to cancel the $k$. That gives $\triangle QPB \sim \triangle QBD$, $BD = AB$, and $QD = \frac{AB^2}{AP}$.
If we choose $D$ to give another roational similarity, then we find that D is also a fixpoint.

With fixpoint D and $QD = \frac{AB^2}{AP}$, we can solve the problem with inversion.

(You may also recognize the structure as midpoint L3A.)

## Original Problem Solution

[//]: # (TODO: add figure)

Based on the reduced version, we can try constructing $\triangle ABP \sim \triangle CQP \sim \triangle DQB$. (This is where
this structure gets its name: we first rotate about $P$ then about $Q$.) This gives $QD \cdot AP = AB \cdot BD$. 
We can speculate that D is a fixpoint, then the problem is solved.

To prove this, we notice that when we constructed the similar triangle, we also constructed $\triangle PBQ$, which is
one of the rotation's second set of similar triangles. We can connect $CD$, and we can find $CD = AB$ via
$\triangle PQB \sim \triangle CQD$ and $\triangle ABP \sim \triangle CQP$. Extend $DC$ to intersect $PB$ at $E$, from rotation,
we find that $PQCE$ are concyclic. $\angle BED = \angle PQC = \angle PBA$ &rArr; $CD \parallel AB$. (Extending $AB$ to
intersect QC also works.) Therefore, $D$ is fixed.

We can also think about constructing the fixpoint D first with the second similarity, then work back to the original rotation.

## Relationships to Other Topics

### L3A

When $ABC$ are collinear, then the first and last triangle in the rolling sequence forms a L3A. When $C$ and $B$ are the
same, it's a midpoint L3A.

However, most of the time, it's a kind of pseudo-L3A where the equal angles do not fall on a single line. The product
relationship still holds up (that's what makes the inversion possible).

This also tells how to construct the intermediate triangle from the first and last:

1. Find the circumcircle $\odot O$ of $\triangle PQB$
2. $\odot O$ intersects $AB$ at $E$
3. Find $C$ on $QE$ s.t. $CD \parallel AB$
4. $\triangle PQC$ is the intermediate triangle.

### Intersecting Lines' Special Case

There, we've discussed three non-linear transformations. This is the next in the series.

## Key Takeaways

1. Analyze relationships between different segments, and construct to make the relationships "simple".
   (Like how the construction here generates parallelogram $ABDC$.) Order of expression is usually useful.
2. Try simpler versions of the problem (special cases) to get of feeling of the problem.

<script>
  window.MathJax = {
    tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
  };
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>