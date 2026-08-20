For problems with easy-to-check local ordering.
## Example
Given a set, find the k-th smallest subset
## Construction
1. Construct a current state. 
	Example: The subset
2. Construct set of transitions to a future state.
	Example: 
	1. Remove the item with largest index + Add the next item
	2. Add the next item directly
3. Make sure every single possible state has **EXACTLY 1** previous state.
	Example:
	1. If the two last items chosen are consecutive, then the previous state is the current set - that last item
	2. Otherwise, the previous state is current set minus - last item + the item before it

If the 3rd step is guaranteed, then the algorithm can be proven to be correct.
It's best if we can have a $O(1)$ transition set, because it can guarantee $O(k \log k)$ time-complexity.
## Side Note
For some problems we can also binary search the answer.
In the example problem, we can do a brute force search (with elements sorted), and if the count reaches k, we can terminate early. Overall complexity $O(n \log n + k \log V)$.
## Reference
https://notes.sshwy.name/K-Greedy/