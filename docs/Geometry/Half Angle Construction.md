# Half Angle Construction

## General Idea

In most cases, two angles with a ratio of 2 can be constructed to give either an angle bisector or an isosceles triangle (or both.)
An isosceles triangle would be preferable, as it already gives a very simple side relationship ($AB = AC$)

<iframe src="https://www.geogebra.org/calculator/hhk3yxhe?embed" width="1200" height="700" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

## Angle Bisector

### Symmetry Construct

This the simplest form of half angle.The figure is symmetric about the angle bisector, so make full use of its symmetry.

<iframe src="https://www.geogebra.org/calculator/me3gusju?embed" width="1200" height="700" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

#### Properties:

1. $AO = BO$
2. $AH = BH$
3. $HC = HD$
4. $AB \perp OH$
5. $HC \perp OA$
6. $HD \perp OB$
7. $OH \,\text{bisects}\, \angle AOB$

### Parallel Construct

Let $OC \,\text{bisects}\, \angle AOB$.

#### Method 1

Construct $BD \parallel OC$ intersects $AO$ at $D$. (Construct line parallel to bisector.) </br>
&rArr; $OD = OB$

<iframe src="https://www.geogebra.org/calculator/tpvykymg?embed" width="1200" height="700" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

#### Method 2

Construct $BD \parallel OA$ intersects $OC$ at $D$. (Construct line parallel to side.) </br>
&rArr; $BO = BD$

<iframe src="https://www.geogebra.org/calculator/aspz2u37?embed" width="1200" height="700" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

### Angle Bisector Theorem

<iframe src="https://www.geogebra.org/calculator/yunbeav7?embed" width="1200" height="700" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

Construction: 

1. $OI \,\text{bisects}\, \angle AOB$ intersects $AB$ at $I$
2. $OJ \,\text{bisects}\, \angle BOC$ intersects $AB$ at $J$

Properties:

1. $\frac{AO}{OB} = \frac{AI}{BI} = \frac{AJ}{BJ}$
2. $\angle IOJ = 90^\circ$

which is basically Apollonius Theorem.

## Co-vertex

This is when $\angle COD = \frac{1}{2} \angle AOB$, where $\triangle AOB$ is an isosceles triangle.

### Basic Idea

<iframe src="https://www.geogebra.org/calculator/wrdqferm?embed" width="1200" height="700" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

Just rotate $\angle AOC$ (and the triangle it's in) about $O$ to $\angle BOD$, then $OD \,\text{bisects}\, \angle COD$.
Make use of the symmetry in the angle bisector.

### Recognition

This is the hardest part of the Co-vertex type.

<iframe src="https://www.geogebra.org/calculator/yxpq7gsv?embed" width="1200" height="700" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

Properties:

1. The circumcenter $I$ of $\triangle BOC$ is on OC.
2. If $\angle AOB = 90^\circ$, $OEFBC$ are all on $\odot I$

### Examples

1. 《核心考点·九上》P82 04

<script>
  window.MathJax = {
    tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
  };
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>