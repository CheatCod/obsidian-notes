**Assumption:** Dictionary is prefix-free: no string is a prefix of another

Assumption satisified if all string have the same length
Assumption satisifed if all strings end with 'end-of-word' character '$'

Example:
![[Pasted image 20221027144719.png]]

Tries::insert(x)
- Search for x, this should be unsuccessful
- Suppose we finish at a node $v$ that is missing a suitable child, expand the tries from node $v$ by adding the neccesary nodes that correspond to extra bits of $x$

# Variations of Tries

Do not store the actual keys at the leaves
- The path already stores the string, therefore we don't need to store the string again


Allow Proper Prefixes

Pruned Tries

