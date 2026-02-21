# Extra Special Case

[//]: # (TODO: add figure)

This is the sA-type but with $\angle OAC = \angle OBA = 90^\circ$.

This condition creates another [coincident rotation](../../Rotation/Basic%20Rotation.md#note) and sA-type as shown bellow.

## Properties

1. $\triangle OAB \sim \triangle OCA \sim \triangle ACB$
2. $OA ^ 2 = OB \cdot OC$ and $AC ^ 2 = BC \cdot OC$ (from sA-type)
3. $AB ^ 2 = OB \cdot CB$ (from coincident rotation)
4. $\frac{OB}{CB} = \frac{AO^2}{AC^2}$ (derived from 2nd)

Here are the results in use:
Let $AO = a$, $AC = b$, $OC = \sqrt{a^2 + b^2}$.

1. $AB = \frac{AO \cdot AC}{OC} = \frac{ab}{\sqrt{a^2 + b^2}}$ (**IMPORTANT**)
2. $OB = \frac{AO ^ 2}{OC} = \frac{a^2}{\sqrt{a^2 + b^2}}$
3. $CB = \frac{AC ^ 2}{OC} = \frac{b^2}{\sqrt{a^2 + b^2}}$

## Usage

1. When a lot of right angles are around (like in L3A with $90^\circ$).
2. As this is a sA-type case, it does generate a Apollonius Circle, and **$AC$ is tangent to $\odot O$**.

<script>
  window.MathJax = {
    tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
  };
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>