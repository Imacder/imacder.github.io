# Trigonometry

## Euler's Formula

$$ e^{ix} = \cos(x) + i \sin(x) $$

Let $u = e^{ix}$, then:

$$ 
\begin{align*}
& \sin(x) = \frac{u - \frac{1}{u}}{2i} \\
& \cos(x) = \frac{u + \frac{1}{u}}{2}
\end{align*}
$$

Useful for subsitution.

Though sometimes we can use:

$$ 
\sin(x) = \frac{a - b}{2} ,\, cos(x) = \frac{a + b}{2} \\
\Rightarrow a^2 + b^2 = 2
$$

## Angle summation

This directly follows from Euler's formula:

$$
\begin{align*}
&\sin(x + y) = \sin(x)\cos(y) + \cos(x)\sin(y) \\
&\cos(x + y) = \cos(x)\cos(y) - \sin(x)\sin(y) = 2 \cos^2(x) - 1 \\
&\tan(x + y) = \frac{\tan(x) + \tan(y)}{1 - \tan(x)\tan(y)}
\end{align*}
$$

## Sine / Cosine Formula

### Sine Formula

$$ \frac{a}{\sin(A)} = \frac{b}{\sin(b)} = \frac{c}{\sin(c)} = d $$

where d is the diameter of the circumcircle. </br>
Used in AAS / ASA / circum-radius calculation. </br>
(The derivation of its relationship to d is in Othocenter.)

Also used for area calculation (or transform triangle area with known angle):

$$ S_{\triangle ABC} = \frac{1}{2} a b \sin(C) = \frac{1}{2} \mathbf{a} \times \mathbf{b} $$

(Examples: R4)

### Cosine Formula

$$ c^2 = a^2 + b^2 - 2ab \cos(C) $$

Used in SSA. Vector dot product's derivation also follows from here.

<script>
  window.MathJax = {
    tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
  };
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>