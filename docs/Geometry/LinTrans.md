# Linear Transformation

## Transformations Written in Linalg Form

### Translation

$$ + \begin{bmatrix} \Delta x \\ \Delta y \end{bmatrix} $$

### Rotation

$$ \begin{bmatrix} \cos(\theta) & -\sin(\theta) \\ \sin(\theta) & \cos(\theta) \end{bmatrix} $$

for counter-clockwise rot

### Dilation

$$ k \mathbf{p} + (1 - k) \mathbf{c} $$

This is basically a weighted sum, where $\mathbf{p}$ is the original point,
and $\mathbf{c}$ is the center of the transformation.

#### Special Case (reflection about point):

$$ 2 \mathbf{c} - \mathbf{p} $$

### Reflection (about line through origin)

$$ \begin{bmatrix} \cos(2 \theta) & \sin(2 \theta) \\ -\sin(2 \theta) & \cos(2 \theta) \end{bmatrix} $$

where $\theta$ is the angle between x-axis and reflection axis. </br>
See [Trigonometry](misc/Trigs.md#angle-summation) for calculation of $\cos(2\theta) \, \sin(2\theta)$ with $\cos(\theta) \, \sin(\theta)$. </br>
For reflection about any line, first do a translation then apply this matrix then translate back.

### [How to Derive These Matrices](misc/Linalg.md#how-to-derive-transformation-matrices)

### Note

Any translation + dilation + rotation (can be about different centers) can be rewritten as a single rotation + scale (about a single point.)

---

## Basic Idea

### Single Point in Motion + Translation

Let $\mathbf{u} = A \mathbf{x} + \mathbf{b}$ </br>
if $\mathbf{v}$ is related to $\mathbf{u}$ via a linear transformation </br>

$$ \begin{align*}
\mathbf{v} & = M \mathbf{u} + \mathbf{d} \\
& = M (A \mathbf{x} + \mathbf{b}) + \mathbf{d} \\
& = \underbrace{M A \mathbf{x}}_{\text{transform orignal motion}} + \underbrace{(M \mathbf{b} + d)}_{\text{transform orignal motion's center}}
\end{align*} $$

#### Example

</br><iframe src="https://www.geogebra.org/calculator/knxvyn36?embed" width="1200" height="700" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe></br>

Transformation in Linalg &rArr; Similar Triangles </br>
($ \triangle BDU \sim \triangle B'DV $, but here's a special case where it is congruent)

### Two Points in Motion

Denote points $A \, B$. </br>
Idea: Transform $AB$ to make either $A'$ or $B'$ stationary. (Often uses translation)

#### Example

</br><iframe src="https://www.geogebra.org/calculator/hcq9rrup?embed" width="1200" height="700" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe></br>

Given equilateral $\triangle ABC$, $CD = BE$. Find $\min(DE)$. </br>
Translates $ED$ to $E'D'$ </br> 
&rArr; $CD = DD' ,\, \angle CDD' = 120^\circ$ </br>
&rArr; $\angle DCD' = 30^\circ$ (locus of $D'$)

For more points, the idea is the same: use some transformations to make points stationary.

---

## Further Examples

* R5 (solvable with Idea 2 but redundant if the original point's path is an arc)

<script>
  window.MathJax = {
    tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
  };
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>