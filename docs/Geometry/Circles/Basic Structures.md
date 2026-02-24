# Basic Structures

## Fixed Length

This is literally the definition. </br>
Occurs in some problems involving folding.

[//]: # (TODO: add graph of fold)

## Fixed Angle

### Case 1: With a Fixed Length

In this case, the vertex traces a fixed circle. There's an even more special case, 
where the angle is $90^\circ$, then the center of the circle is the midpoint of the fixed segment。

And every chord / arc have a corresponding angle. In some cases, the corresponding angle is given, 
and it can be used to derive other angles directly. When the radius of the circle and the chord length are given, 
we'll have to calculate its corresponding angle. The most common case is with the diameter.

#### Examples:

1. Incenter path
2. Foot of some perpendicular construction (as shown below)

[//]: # (TODO: add graph)

### Case 2: Without Fixed Length

Let $\angle ABC = \theta$. </br>
In this case, constructing the circum circle might still be useful, as it creates a relationship between $AB$
and $r_{\odot}$, namely:

$$ AB = 2 \sin(\theta) r_{\odot} $$

#### Examples:

1. Spotlight (shown below)
2. R5

[//]: # (TODO: add graph)

## Fixed Ratio + Fixed Length

This is Apollonius Circle Theorem (also mentioned in [Half Angle Construction](../Half%20Angle%20Construction.md#angle-bisector-theorem).) </br>
Obviously you can use the Angle Bisector Theorem to derive this, but there's a better way:

[//]: # (TODO: add graph)

Let segment be $AB$, and $\frac{CA}{CB} = k$. The $C$ traces $\odot O$.

$$
\begin{align*}
& \triangle OCA \sim \triangle OBC \\
\Rightarrow & \frac{OA}{OC}=\frac{OC}{OB}=\frac{AC}{BC}=k \\
\Rightarrow & r = \frac{k}{1 - k^2} AB \,\, \text{(assuming k < 1)}
\end{align*}
$$

### Examples

#### Minimize Distance

This is the standard application, where the circle is given and $BC$ is given, and you need to construct $AC=kBC$.
Same method as above.

[//]: # (TODO: add graph)

#### Minimize Ratio

Consider what happens when $k$ is decreased from $1$: the radius of the circle also decreases. So there must be a point
where $C$ cannot satisfy being on the circle (so ratio is correct) and the other constraints of the problem. This is
the minimum.

However, this is not the standard way to solve the problem. Most of the time, we can construct a rotation (or some other similar triangle) to transform the
ratio into a distance. Then we can use methods like [inversion](../Line%20Construction/Intersecting%20Lines/Special%20Case.md#inversion) or something to find the path of one end.

There is also another way to use this, by seeing the circle AS the Apollonius Circle, and constructing the second
end point. See R(n) for details.

## Equal Angles

**Any** two equal angles (except when their legs are parallel) will produce four points that are concyclic.

### Construction

Extend the legs of the two angles so they intersect. The extension may be backwards.

When the vertex of one angle is on another's leg, then that leg is tangent to the circle.

[//]: # (TODO: add graph)

### Application

This is usually used to relate two equal angles.

### Note

All the angle relationships in the circle can be obtained without the circle but with [similar triangles](Similar%20Triangles%20in%20Circle.md#basic-similarities).

<script>
  window.MathJax = {
    tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
  };
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>