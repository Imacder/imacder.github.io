We maintain a set of $2$ numbers ${a, b}$ that might contain $0$.
When we add a new number $c$ in:
1. $\gcd(a,b) = \gcd(a,c)$, then $a$ is non-zero
2. $\gcd(a,b) < \gcd(a,c)$, then $b$ is non-zero
3. $\gcd(a,b) > \gcd(a,c)$, then $c$ is non-zero
This yields a solution $\mathcal{O}(2n - 4)$.