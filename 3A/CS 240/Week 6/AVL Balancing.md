
An important weakness in the Module 4 slides (describing when to do which rotation)

For **Slide 24**: 

When rebalancing a tree rooted by $z$
1. Let $y$ be the taller child of $z$
2. Let $x$ be the taller child of $y$ (no gaurentee that $y$ will have different height children)
if $y$'s children have equal height, ie, the balance factor of y is 0, then:

There are 2 classes of rotations: **Single Rotation** vs **Double Rotation**

Single rotation is prefered since they require fewer steps.

Thus, if possible, choose $x$ to satisfy 
$$x > y > z$$
or $$x < y < z$$
ONLY IF the balance factor of $y$ has opposite sign to that of $z$ should a double rotation be performed.

zig zag: ![[Pasted image 20221018151634.png]]