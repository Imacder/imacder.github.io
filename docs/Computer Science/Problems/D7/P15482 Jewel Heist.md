## Step 1

If the problem instead takes all jewels with $l \le x \le r$, then the problem is a typical 2-pointers. But there is this choice of where to make the cut in the y-axis.

## Step 2

We instead consider sweeping the y-axis and se how we can split the x-axis. Do we do CDQ on x?

## Solution

Instead we consider iterating over every color. The time complexity is correct because of amortized analysis. We can do a sweep line as usual, but now we split the query range whenever we come across a forbidden color.

**Details TO BE CLARIFIED**