To solve equations like:
$$f(x) = a_0 x + b_0 + \sum_{i=1}^k \left\lfloor \frac{a_i x + b_i}{c_i} \right\rfloor \ge 0$$
We can find the LCM of all $c_i$, then we can do substitution:
$$x = Mq + r$$
Plugging this into the inequality:
$$\left\lfloor \frac{a_i (Mq + r) + b_i}{c_i} \right\rfloor = \frac{a_i M}{c_i} q + \left\lfloor \frac{a_i r + b_i}{c_i} \right\rfloor$$
We iterate over all $0 \le q < M$. For each $q$, we have:
$$Aq - B \ge 0 \, (A > 0)$$
$$q \ge \left\lceil \frac{B}{A} \right\rceil = \left\lfloor \frac{B + A - 1}{A} \right\rfloor$$
If the inequality is flipped:
$$Aq - B \le 0 \, (A > 0)$$
$$q \le \left\lfloor \frac{B}{A} \right\rfloor$$
(Note: C++ rounds toward $0$, must write a custom function for floor / ceil)