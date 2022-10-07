# Dictionary

**Dictionary**: An ADT consisting of a collection of items, each of which contains
- a key
- a value

KVP

## BST

Search:

Start at root, compare $k$ to current node's key, stop if found or subtree is empty

Delete:

First search for the node $x$ that contains the key
- If $x$ is a leaf, delete it
- If $X$ has one non-empty subtree, move child up
- Else, swap key at $x$ with key at successor or predecessor node and then delete that node


### Height
search, insert, and delete all have cost of $\Theta(h)$, where $h$ is the height of the tree

## AVL Trees

AVL tree is a BST with an additional **height-balance property**:

The heights of the left and right subtree differ by at most 1.

The height of an empty tree is define to be -1

If node $v$ has left subtree $L$ and right subtree $R$, then

$$
balance(v) = height(R) - height(L) \in \set{-1, 0, 1}
$$


-1 means $v$ is *left heavy*
0 means $v$ is *balanced*
1 means $v$ is *right-heavy*

Prove that an AVL tree having $n$ nodes has $\Theta(\log n)$ height

Normally we would fix an AVGL tree having n nodes, then determine the max possible height 

It turns out that in this case, its is easier to fix the height $h$, then ask the minimum # of nodes we need to realize that height.

Define $N(h)$ = smallest # of nodes in an AVL tree having height $h$

Claim: $N(h) \ge c^h$, for some constant $c > 1$

Establishing this claim will immediately prove the theorem:

Any AVL-tree with $n$ nodes, and height $h$ satisify:

$n \ge N(h) \ge c^h$, there fre $c^h \le n$, $h \le \log c n \in O(\log n)$

**First proof (easier to understand)**

We show that $N(h) \ge 2^{\frac{h}{2}} = \sqrt{2}^h$, by induction on $h$

Base case:

$h=0 \lor h =1$:

Inductive ($h \ge 2$)

Both subtree have height at least $h-2$(could be better but not needed)

So both subtree must have at least $N(h-2)$ nodes, and therefore

$$N(h) \ge N(h-2) \ge 2 \cdot c^{\frac{h-2}{2}} = 2^{\frac{h}{2}}$$

**Second proof**

GIven the biggest possible choice for $c$

Base case:

Induction: 

$h=1$ means we must have 2 or 3 nodes, minimum # of nodes for height 1 is 2.

Consider a tree of height of $h \ge 2$It could be that both subtress have height $h-1$ but this does not give the minimum number of nodes, thus one subtree has height $h-1$, the other has height $h-2$



