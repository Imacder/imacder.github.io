# L3A

## Construction

[//]: # (TODO: add graph)

Given an angle ($\angle AMB$) in an odd orientation.

Obviously we can use a rotation, but sometimes that doesn't connect to the conditions given directly. Then we might be
required to translate the rotated result to another position (essentially constructing a parallelogram.)

This is basically L3A.

1. Construct a line in the "normal" direction going through $A$.
2. Find two point on the line satisfying $\angle ACM = \angle AMB = \angle MDB$.
3. $\triangle ACM \sim \triangle MDB$ ($AC \cdot MC = BC \cdot  MD$)

## Variations

### Middle Intersection

[//]: # (TODO: add graph)

Instead of an angle with rays, we're given two lines with a rotational angle. The most common structure is the lines
inscribed in a parallelogram.

We can translate again, but that is slow. We can actually construct the original similarity (but translated) directly.
That may speed things up a lot.

### Midpoint L3A

[//]: # (TODO: add graph)

When $M$ is the midpoint of $CD$, then this becomes a [rolling similarity](Rolling%20Similarity.md#l3a). (i.e.
$\triangle ACM \sim \triangle AMB \sim \triangle MDB$, $A$ and $B$ are the rotational centers.)

This case only occurs when $CD$ doesn't pass through the interior of $\angle AMB$. When it does, then this reduces to
[coincident rotation](Basic%20Rotation.md#note).

#### Special Property

Extend $AC$ and $BD$ to intersect at $E$.

$AM$ and $BM$ bisects $\angle CAB$ and $\angle DBA$ &rArr; $M$ is the incenter of $\triangle ABE$.

### Parallel Sides

[//]: # (TODO: add graph)

Instead of $\angle ACM = \angle MDB$, we have $\angle MAC = \angle AMB = \angle MDB$ &rArr; $AC \parallel MB$.

Used to [transform ratios](../Line%20Construction/Parallel%20Lines/Basic%20Structure.md).

(Only usage I've seen is in 《核心考点·中考数学》P17 02)

### Rotation and Chordal Graph

The L3A similarity can also be seen as a rotation itself.

[//]: # (TODO: add graph)

In a regular polygon, the triangle can be rotated multiple times to give the chordal graph.

It also gives a new type of L3A with one end constrained to one of the vertices of the polygon, and another end walking
on an adjacent side.

[//]: # (TODO: add graph)

Usually the rotation is just a tool for thinking, rather than an actual step in problem-solving. In the cases 
(e.g. 某年天河期末 R6) where the rotation is actually a crucial step, we can usually combine the corresponding sides in
different types of chordal graph to construct a new rotational pair.

## Usage

1. Transform angles (or triangles) in an odd orientation.
2. Find intersections of a circle and line (《核心考点·中考数学》P30 03). This is a special application of the first use case.
