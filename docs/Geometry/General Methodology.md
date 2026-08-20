## What is Geometry Actually Doing?

Geometry is essentially solving a system of equations. Because the points live in 2d, we need 2 variables (degrees of freedom, or DoF) to define where exactly a point is. (There are caveats like space-filling curves, but we ignore these for now.) Each condition is an equation.

2 basic properties:
1. If a problem has $2n - 3$ independent conditions (where $n$ is the number of points), then the figure is rigid / isostatic (it's shape and size is locked in to a finite number of states.)
2. If a problem has $2n - 4$ independent conditions, and no information about absolute size is given, the figure's shape is fixed.

With this insight, we can already build a deterministic geometry solver with a Gröbner Basis. We simply take all the conditions and eliminate the variables. The equation we are trying to prove is true iff it's fully reducible by the basis. If it's finding a particular value, then we eliminate the expression in the basis. There are other deterministic methods based on the same idea, like the Area Method.

However, these kinds of methods usually yield solutions that are extremely hard for humans to understand let alone execute.

## Synthetic Geometry

With the goal of elimination in mind, we can apply this to synthetic geometry. Essentially, we are trying to reduce the number of points in the problem. We have 2 main solving strategies / directions / ideas: Reverse Engineer & Kinematics. They are not mutually exclusive, some problems might need both.

### Reverse Engineer

#### Step 1

First we do some basic analysis on the figure. We need to segment the figure into multiple sub-figures to make the solving steps easier, using the following 2 methods:
1. Segment based on the construction steps. If the problem statement says "construct this first", then we can segment it into a section.
2. Segment based on DoF. This is easier for rigid figures, we can just find sub-figures that are also rigid and solve those first. For non-rigid figures, we need to sub-figures that may generate new conditions to replace old ones (maybe even remove some points altogether) (# of deleted points = $2 \,\times$ (original conditions - generated conditions)).

We can also rely on some symmetrical structure for segmentation.

#### Step 2

We reduce the sub-figures recursively. If a section definitely deletes a point, then it definitely reduces the problem complexity, otherwise it just transforms the problem statement.

Instead of blindly reducing it, we can first make educated guesses then prove them. One type of guess is you directly incorporate the objective you want to prove into the conditions list, then find some properties, this is guaranteed to be correct.

When no property is apparent, we can do some construction based on empirical results (e.g. ratio &rarr; dilation, product &rarr; power of a point, rotation, etc.). These constructs may transform the original conditions so that they are more "canonical" and therefore easier to connect to other conditions. Usually this is made to counter a certain condition, the same way we take the square root to counter squaring.

Note that this kind of construction needs to be done carefully and with the reduction objective in mind, as in the end, ***we have to make sure that we do not increase the number of points after the entire construction chain*** (this is true for any construction). 

Usually with these 2 reduction ideas, some progress can be made. If not, it just might be that it's not solvable. (The smallest case I found that you cannot solve only contains 4 points, so this is very probable.)

### Kinematics

We can lock down certain points that forms a rigid basis, then move a point around to see how it effects to other points. Works best for figures with 1~2 net DoF.

We usually lock down the largest section possible. We can treat the effects of the main point on the other points as a transformation (including Möbius and Linear). Sometimes we can guess what kind of locus does a point trace by analyzing points at infinity. The details can be seen the dedicated articles about transformations.

Sometimes, we intentionally relax certain conditions (split them into 2 groups) so the point traces a locus under the conditions in each group instead of being completely rigid. Then we find the intersection of the 2 locus with Analytic Euclidean Geometry.