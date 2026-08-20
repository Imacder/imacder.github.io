## Step 1

There is an easy way to check if an $a$ can be generated. We simply roll back from the last modification to the first. Because the modification at time $t$ haven't been modified at $t$, there will be a contiguous segment in the place of modification. When we roll this back, we can find such contiguous segments (we consider $0$ to be any color), and we set it to $0$. 

## Step 2

We find that considering if this thing **CAN** be done is difficult, so we flip this problem around. When this 