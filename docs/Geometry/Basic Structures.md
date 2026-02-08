# Basic Structures and Ideas

This is basically a cheatsheet of all the useful structures.

## List of Structures

1. [Fixed Length &rArr; Circle](Circles/Basic%20Structures.md#fixed-length)
2. [Fixed Angle + Fixed Length &rArr; Circle](Circles/Basic%20Structures.md#fixed-angle)
3. [Fixed Ratio to Fixed Endpoints &rArr; Circle](Circles/Basic%20Structures.md#fixed-ratio-fixed-length)
4. All the [Linear Transformation](LinTrans.md) Techniques
5. Reflection About Circle

## List of Ideas

1. Any construction you made must connect ast least 2 conditions. Otherwise, it would be a dangling construction,
    and the amount of information you can get out of this auxiliary constructing is the same as the amount you
    constructed, so you will get no new information.
2. After constructing auxiliary lines, try to reframe the original problem in the new (simple) figure.
3. Try to find relationships between all angles and segments to see if there is some special relationship if there
    is no clear path forward.
4. Try to use transformation to ensure the parts you are trying to relate are in the same orientation, scale, and chirality.

## Reflection About Circle

### Definition

Given a point $P$, the center of reflection $O$, and the radius of reflection $r$.

The reflected point $P'$ is on ray $\overset{\Large\rightarrow}{OP}$, and $OP \cdot OP' = r^2$.

### Properties and Derivation

<iframe src="https://www.geogebra.org/calculator/jwm9xyet?embed" width="1200" height="700" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

The reflection of a circle is another circle. Here lines are considered circles of $r = \infty$.

Derivation:

1. Construct the diameter ($MN$) of $\odot A$ that goes through $O$ &rArr; $\angle MPN = 90^\circ$
2. Construct the reflection ($M'N'$) of $MN$ &rArr; $\triangle OPM \sim \triangle OM'P' ,\, \triangle OPN \sim \triangle ON'P'$
3. $\angle M'P'N' = 90^\circ$ &rArr; $P'$ is on a circle with diameter $M'N'$

<script>
  window.MathJax = {
    tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
  };
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>