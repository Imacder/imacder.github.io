## Inversion

Given a point $P$, the center of inversion $O$, and the radius of inversion $r$.
The inverted point $P'$ is on ray $\overset{\Large\rightarrow}{OP}$, and $OP \cdot OP' = r^2$.

## Möbius Transformation

We add rotations and translations to inversions (rotations, translation and inversions are all optional). Any 2 similar triangles each with a fixed (in location) edge (so there is only 2 DoF in 1 point) defines a Mobius transformation, though this is not in canonical form (i.e. there are infinitely many pairs of these kinds of similar triangles that give the same transformation). We can also express this in complex function form:
$$f(x) = \frac{ax + b}{cx + d}$$
We can easily see that if we use the definition above, we need to provide a fix point for that other 3 points to be fixed (because we have an extra 2 DoF). We can also use this definition so check if a transformations is a mobius transformation.

Some basic properties:
1. The inverse of a mobius transformation is a mobius transformation.
2. Compositing mobius transformations gives a mobius transformation.

By 1, we can find the point for $f$ and $x$ that causes the other to diverge off to infinity (call it $f_\infty$ and $x_\infty$). Then the transformation would have to be $\triangle x x_\infty a \sim \triangle f(a) f_\infty f(x)$, where $x$ is the point being transformed. Then the canonical form (fixed-point equation) is the case where $a = f(a)$. However this is rarely useful, and we usually chose arbitrary $a$. 

We can use this to prove a transformation is a mobius transformation geometrically. We just need to find where the divergence happens, and find a pair of transformation points (fixed). Now we get the geometric construction, we can just find the proof. Typically, we need only to find $x_\infty$ and the pair of transformation points, $f_\infty$ can be eyeballed then tested.

>[!example] Example 1: Rolling Similarity
>We can denote the rotation + dilation $R$. When we rotate one of the given segments, we get $Rx$. Therefore we need to reverse it by dividing by $R$ for the new segment, hence the second spiral similarity. In this way, we can get another fix point, fulfilling the requirements for a mobius transformation.

>[!example] Example 2
>Given $\triangle AXY$, and $\triangle XOY$ where $O$ and the shape of $\triangle XOY$ is fixed. $\triangle BX'Y' \sim \triangle AXY$, $B$ and $X'$ are fixed. Find the transformation.
>We can choose $O$ as $a$, and the $x_\infty$ is simply $A$. $f_\infty$ is harder to find though. We can drag $X$ all the way to infinity and see where $f(x)$ lands, this reveals that $\triangle f_\infty B X' \sim \triangle XOY$. Simple geometric deduction will prove the mobius transformation.

## Conformity

Any $\angle AXB$ will preserve its size after transformation iff $ABx_\infty$ is collinear. This means that circles transform into circles.

### Apollonius  Circles

The most obvious connection of this to inversions is that the inner and outer points (call them $A$ and $B$ respectively) are reflections about the Apollonius Circle $\odot O$. This can be proven via the usual construction.

Furthermore, we can look at the intersection of $AB$ and $\odot O$ (call it $M$.) When connecting it to a point on the circle $P$, $PM$ bisects $\angle APB$. This is directly due to conformity. (This is also linked to the Angle Bisector Theorem.)

With conformity, we can even extend Apollonius Circles. Given 2 concurrent segments $AB$ and $CD$, if $\angle APB = \angle CPD$, then $P$ traces out a circle. The proof also uses a inversion. We can also show that when they are not concurrent, then it traces out a much more complex 4th order curve.