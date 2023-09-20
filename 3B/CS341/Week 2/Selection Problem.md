
Choose a pivot element $y$, restructure $A$ so that all elements less than $y$ precede $y$ in $A$, and all elements greater occur after $y$.

# Optimistic Analysis

If the pivot ended up in the middle of the array, ($i_y = \frac{n}{2}$), then we recurse on $\frac{n}{2}$ elements

If we could always recurse on $\frac{n}{2}$ elements then

$$
T(n) = T(\frac{n}{2}) + \Theta(n)
$$
which is $O(n)$
# Worst case

If we always get $i_y=1$, and recurse on the right, then
$$
T(n) = T(n-1) + \Theta(n)
$$
which is  $O(n^2)$

# Average case

Definition (almost arbitrary): we say that a pivot $y$ is good if $i_y  \in (\frac{n}{4}, \frac{3n}{4})$
![[Pasted image 20230919131615.png]]

If the pivot element lands in the yellow region we say its good, otherwise bad.

For any good pivot, we recurse on at most $\frac{3n}{4}$ elements

The probability of a pivot element landing in the good zone is 50%

# Proof sketch

- The probability of a good pivot is $\frac{1}{2}$
- On average, after every two recursive calls, we will get a good pivot
- Encountering a good pivot reduces problem size to at most $\frac{3n}{4}$

# Making quick-select linear on worst case 

Median-of-medians QuickSelect

- Similar to QuickSelect

Why find the median of medians?

Cannot just find the median as that will involve solving a $n$ size problem, splitting into subproblems so we can assume subproblems work.

How good is this pivot?

It's an approximately good median, but definitely a good pivot.

Why choose 14 for base case?

With 15 elements we get 3 row of 5 elements which gets you a nice median





# Recurrence

![[Pasted image 20230919141256.png]]

The infinity sum gives a upper bound, as we ignore the base case.

This is only possible since $1/2 + 7/10 = 9/20$ which is less than 1, thus we can plug in a geometric sum formula.

