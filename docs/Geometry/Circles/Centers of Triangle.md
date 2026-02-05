# Centers of a Triangle

Let the trangle be $\triangle ABC$ and its circumcenter be $O$.

## Incenter

Let the triangle's incenter be $I$.

### Idea

1. [Half Angle Construction](../Half%20Angle%20Construction.md)
2. If $I$ happens to be a midpoint ($D$) of two points each on $AB ,\, AC$ ($E,\,F$), then:

   * This is the special case below
   * $\triangle BED \sim \triangle DFC$ (midpoint L3A)

3. Construct the tangent points

### Path

When $\angle A$ is fixed (i.e. A is on a circle), then $\angle BIC = 90^\circ + \frac{1}{2} \angle A$ is also a fixed angle.
Thus, $I$ is also on a circle whose center is the midpoint ($M$) of $\overset{\Large\frown}{BC}$.

### Special Case

#### Condition

$$ \angle AIO = 90^\circ $$

#### Properties

1. $OI$ is tangent to $\odot M$.
2. Extend $AI$ to intersect BC at $D$, then $DI = MI = \frac{1}{2} AI = \frac{1}{4} AM$.
3. $AB + AC = 2 BC$
4. Idea 2

## Othocenter

Let the othocenter be $H$, and the foot of the three heights be $I$ (which is on $AB$), $J$ (on $BC$), and $K$ (on $AC$).

### Properties of $\triangle IJK$

1. Of all the triangles with points on each of $AB,\,BC,\,AC$, $\triangle IJK$ has the least circumference.
2. $H$ is the incenter of $\triangle IJK$.
3. Concyclic Groups:

    * $ABJK$
    * $BCIK$
    * $ACIJ$
    * $AIKH$
    * $BIJH$
    * $CJKH$
   
### Idea

Extend $AO ,\, AH$ to intersect $\odot O$ at $D ,\, E$, then:

1. Produces parallelogram $BDCH$
2. $BC \parallel DE$

### Properties

1. Let the distance from $O$ to $BC$ be $a$, then $AH = 2a$
2. $2r = d = \frac{AB \cdot AC}{AD}$ </br>
   Derivation: Extend $BO$ to intersect $\odot O$ at $P$, then $\triangle ABP \sim \triangle DAC$
3. If $\angle BAC = 60^\circ$, then $AO = AH$.

## Other Centers

These centers are not strictly related to the circle.

### Centroid

Let the centroid be $G$. 

#### Property

Extend $AG$ to intersect $BC$ at $D$, then $AG = 2DG$.

### Fermat's Point

Let the Fermat's point be $P$.

#### Properties

1. Of all points in the plane, $P$ minimizes $AP + BP + CP$. (Derived through [rotation](../Rotation/Basic%20Rotation.md))
2. $\angle APB = \angle BPC = \angle APC = 120^\circ$
3. Construction of $P$: Construct equilateral triangles with $AB ,\, BC ,\, AC$ as sides, 
    then connect the other vertex of the equilateral triangle with the other vertex of $\triangle ABC$. Their intersection is $P$.

<script>
  window.MathJax = {
    tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
  };
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>