# Analytic Euclidean Geometry

As the name suggests, we try to use Euclidean Geometry to replace Analytic Geometry, while keeping the ideas of analytic geometry.

## Basics

We try to choose a foundation (like choosing the axes of normal Analytic Geometry). We try to choose whatever foundation
that keeps the most points / segments stationary.

Then we can build the figure with [Basic Structures](Basic%20Structures%20and%20Ideas.md#list-of-structures). There may
be points that require two conditions to fix, so you need to find the intersection of two elements.

## Intersection

### Line to Line

#### Characterization 1

Two Angles + Fixed Distance

Solution:
Construct height of the triangle, then use [Trigonometry](./misc/Trigs.md).

It doesn't have to be the height, however, $90^\circ$ is the easiest to work with.

#### Characterization 2

Two Fixpoints &rArr; Line

In this case, we can manually calculate the trig (or something similar) value of the angle in Characterization 1.
Then we can just use the solution above.

Or you can use a Cartesian / Skew Coordinate System, by construction the decomposed vectors in that coordinate system.
With the fixed angle, you can get two pairs similar triangles + a displacement.

#### Characterization 3

3 Know Endpoints + Know Angle in between

Solution: Connect 2 endpoints and solve the triangle (AAS?)

### Line to Circle

#### Characterization 1

Fixed Center + Fixed Length &rArr; Circle

Solution 1:
Drop a perpendicular line through the center of the circle and find the height. The distance from the foot to the intersection is $\sqrt{r^2-h^2}$.

#### Characterization 2

Fixed Angle+ Fixed Length &rArr; Circle

Solution 2:
Construct a equal angle and use [Intersecting Lines](./Line%20Construction/Intersecting%20Lines/index.md).

(Note: Solution 2 isn't always the best option, sometimes we convert it into characterization 1 to solve it.)

### Circle to Circle

#### Characterization

Fixed Center + Fixed Length &rArr; Circle </br>
(The other characterizations must be converted into this)

Solution: Connect the centers of the circles. Along with the known radii, we can solve the triangle with SSS.
