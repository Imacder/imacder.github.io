# Basic Rotation

Essentially this is $\triangle OAB \sim \triangle OCD$.
Or you can understand this at segment rotation.

<iframe src="https://www.geogebra.org/calculator/swgeweve?embed" width="1200" height="700" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

## Properties

1. $\triangle OAB \sim \triangle OCD \Leftrightarrow \triangle OAC \sim \triangle OBD$
2. Concyclic Groups (from Angle Rotation): 
    * $ACIO$
    * $BDIO$
    * $ABJO$
    * $CDJO$

#### Note

These properties reduce when $(B,C)$ or $(A,D)$ are the same. </br>
Specifically: 

1. the 1st property reduces completely.
2. the 2nd property:
    * $CD$ is tangent to $\odot OAB$
    * $AB$ is tangent to $\odot OCD$

For the concyclic properties, see Angle Rotation for more information.

## Finding Rotational Center

<iframe src="https://www.geogebra.org/calculator/pdkmm5jq?embed" width="1200" height="700" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

Let segments be $AB ,\, A'B'$

1. Find the segments' intersection $S$
2. Construct $\odot ASA' ,\, \odot BSB'$
3. The circle's intersection (other that $S$) is the rotational center

This is AA construction + derive from concyclic points.

#### Note
If S is the same as $A / B / C / D$, then construct tangent circles (in property notes.)

## Construction

1. AA
2. SAS (with O as vertex)

## Derivation

1. SAS with $A$, $B$, $C$, or $D$ as vertex
2. Derive back from concyclic property (construction 1)
3. From the other pair in property 1 (construction 2)

## Examples

1. To add / subtract segments:
    * 《核心考点·中考数学》P34 06
    * Ptolemy's Theorem
2. (P)oint in Triangle:
    * Idea: connect $PA ,\, PB ,\, PC$, then rotate appropriate triangle out (e.g. $\triangle ABP \rightarrow \triangle BCP'$)
    * P34 07 08
    * Fermat's Point
    * P42
3. derivation 1: P34 05
4. derivation 2: P34 06
5. derivation 3: R4

<script>
  window.MathJax = {
    tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
  };
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>