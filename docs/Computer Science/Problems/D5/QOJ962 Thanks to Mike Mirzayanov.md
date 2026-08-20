## Step 1

We can batch the permutation and reverse the all the segments as a whole. The potential function for this is difficult to calculate. maybe we can try to D&C.  Say we do a sort of quicksort. At each timepoint we basically want to sort a 0/1 array.

## Step 2

There is no way to preserve the answer naively. We basically need to join the different segments up. We can only look at adjacent batches. We want (1100)(0011) alternating, then we can join them. The thing is this may not be so easy to do. (01)(0)(10)(1)(01)(0)(10)(1) -> 110001110001 Maybe we can do (1...10...0)(1....1)(0...01....1)(0...0) -> (0...0)(0...01...1)(1...1)(1...10...0) we can join three of them together so $\log_3(n)$ per op.

We can do this in parallel for each layer of quicksort and the total complexity is $\mathcal{O}(\log^2 n)$.

## CF1427D