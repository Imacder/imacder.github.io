# Introduction

This is one of the two main parts of similar triangles (the other is [Intersecting Lines](../Intersecting%20Lines/index.md).)

## Basic Idea

This is a way to scale (dilate) a sub-figure to some size (or orientation, when factor $k < 0$), so that we can obtain its relationship to other structures at this same scale.

## Construction Criteria

1. DO NOT split current / to be solved ratios, unless there is no other path forward. (Otherwise you'll end up with a mess of equations if you can solve it at all.)
2. Any construction (path) made here must link at least 2 parameters. Think of this as a graph search: for any path from start to end, there is 1 LESS edge than vertex.

<script>
  window.MathJax = {
    tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
  };
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>