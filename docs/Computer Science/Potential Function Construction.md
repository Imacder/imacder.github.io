### Step 1: Define the Mathematical Goal

For amortized analysis or cost-bounding problems, the defining rule of a potential function $\Phi$ is how it changes during an operation.

Let $c$ be the actual cost of a move. You want to define an amortized cost (let's call it $a$) that is either zero or a known constant. The fundamental equation is:

$$a = c + \Delta\Phi$$

In the permutation problem we just looked at, we wanted the potential to drop by exactly the cost of the move, meaning the amortized cost $a$ should be $0$.

Therefore, our mathematical constraint is:

$$\Delta\Phi = -c$$

### Step 2: Parametrize a "Candidate" Function

Next, you brainstorm the _features_ of the state that change when you make a move. For arrays and permutations, the common features are:

- $I$: Number of inversions
    
- $D$: Sum of absolute distances ($\sum \vert{}P_k - k\vert{}$)
    
- $C$: Number of cycles in the permutation graph
    

Instead of guessing which one is the perfect fit, you combine them with unknown coefficients ($\alpha, \beta, \gamma$):

$$\Phi(P) = \alpha D + \beta I + \gamma C$$

### Step 3: Set up the Equations (The Derivation)

Now, you analyze a single, generic operation and see how your features change.

Let's say we only looked at $D$ (absolute distance) for our permutation problem. We set our candidate function as:

$$\Phi(P) = \alpha D = \alpha \sum_{k=1}^N \vert{}P_k - k\vert{}$$

We know from our previous analysis that if we swap $i$ and $j$ ideally, the total absolute distance $D$ decreases by exactly $2(j - i)$.

Therefore:

$$\Delta D = -2(j - i)$$

Now, we plug this into our potential function's change:

$$\Delta\Phi = \alpha(\Delta D) = \alpha(-2(j - i))$$

Finally, we force this to equal our mathematical goal from Step 1 ($\Delta\Phi = -c$), where the cost $c = j - i$:

$$\alpha(-2(j - i)) = -(j - i)$$

### Step 4: Solve for the Coefficients

Now, it's just basic algebra! Divide both sides by $-(j - i)$:

$$2\alpha = 1$$

$$\alpha = \frac{1}{2}$$

**Boom. No guessing required.** The math tells you that if you want to use the absolute distance $D$, you _must_ multiply it by $\frac{1}{2}$ to make it a valid potential function.

### What if you picked the wrong feature?

Let's say you decided to try deriving it using inversions ($I$) instead of distance ($D$).

Candidate: $\Phi(P) = \beta I$

We established earlier that one move changes inversions by:

$$\Delta I = -(2(j - i) - 1)$$

Plug it into our goal ($\Delta\Phi = -c$):

$$\beta \Delta I = -(j - i)$$

$$\beta (-(2(j - i) - 1)) = -(j - i)$$

Try to solve for $\beta$:

$$\beta = \frac{j - i}{2(j - i) - 1}$$

Here, $\beta$ is not a constant! It depends on $i$ and $j$. This is the math explicitly telling you: _"Hey, a standard inversion count alone cannot form a valid potential function for this specific cost structure, because the scaling factor changes depending on how wide the swap is."_

### The Takeaway

To mathematically derive a potential function:

1. Write down the equation: $\Delta\Phi = -\text{Cost}$ (or $\le -\text{Cost}$).
    
2. Create a generic function with unknown variables (like $\alpha, \beta$).
    
3. Calculate how your generic function changes during one move.
    
4. Set that change equal to your goal and solve for the variables.

### Example: Small to Large Merging

For merging set $A$ into another set $B$, we need:
$$\Delta \Phi <= -|A|$$
Furthermore, we need the potential to be easy to calculate:
$$\sum f(|S_i|) = \Phi$$
Thus:
$$f(|A| + |B|) - f(|A|) - f(|B|) <= -|A|$$
This is a functional equation.
$$f(x) = -kx\ln{x}$$
Therefore the whole process is $O(n\log n)$
