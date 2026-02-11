# Similar Triangles in Circle

## Construct

Quadrilateral $ABCD$ is inscribed in $\odot O$. $AC$ and $BD$ intersects at $E$. Extend $AB ,\, DC$ to intersect at $F$.

[//]: # (TODO: add graph)

## Basic Similarities

### Inside Quadrilateral

$$ \triangle ABE \sim \triangle DCE $$
$$ \triangle BCE \sim \triangle ADE $$

These pairs give relationships for segments **INSIDE** the quadrilateral.

### Outside Quadrilateral

$$ \triangle FBC \sim \triangle FDA $$
$$ \triangle FAD \sim \triangle FCB $$

These pairs give relationships for segments **OUTSIDE** the quadrilateral.

## Ptolemy's Theorem

[//]: # (TODO: add graph)

$$ \left| AB \cdot CD - AD \cdot BC \right| \leq AC \cdot BD \leq AB \cdot CD + AD \cdot BC $$

### Equality Case

When the left side is equal, $(A,\,C,\,B,\,D)$ (or $(A,\,B,\,D,\,C)$, in order) is concyclic.

When the right side is equal, $(A,\,B,\,C,\,D)$ is concyclic.

### Derivation

Construct rotation on $\angle BAC = \angle BDC$. Specifically choose point $G$ on $AC$ s.t. $\angle ABG = \angle DBC$.
Then use the double similarity to solve.

### Usage

Used to find inequality relationships in a quadrilateral. Best used when the other axis of freedom are homogeneous when 
written down.

This is also the **IN-OUT** relationship part.

## Special Case

### Condition

$$ AB = CB $$

### Properties

1. The similarity in the Ptolemy case reduces to congruency, giving: $AD + BD = 2 AB \sin ABC $
2. Inv-A Similarity: $\triangle BAE \sim \triangle BDA$
3. Collinear Rotation: $\triangle BDA \sim \triangle CDE$

<script>
  window.MathJax = {
    tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
  };
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>