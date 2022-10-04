# Ambiguity cont

If $R$ is a regex producing $R \in \set{0,1}^*$

$R$ is *unambiguous* when 

every string in $\set{0,1}^*$ is produced at most once
every string in $R$ is produced exactly once

$R$ is *ambiguous* when

some string in $\set{0,1}^*$ or in $R$ is produced at least twice

# Block Decomposition

Block decompsitions are always unambiguous

Ex Block of 0s have even length:

Block of 1s: $\set{1,11,111,111...}$ produced uniquely by $1^*1$

Block of 0s: $\set{00,0000,000000...}$ produced uniquely by $(00)^*00$

Block of 0s followed by a block of 1s: $(00)^*001^*1$

repeated arbitrarily many times: $((00)^*001^*1)^*$

Add preamble and postamble: maybe start with1s, or end with 0s:

$$1^*((00)^*001^*1)^*(00)^*$$


> [!note] 
> Not every unambiguous expression is a block decomposition!

Ex.

$(0 \cup 1)^*$ produces every binary string exactly once bit by bit


Ex. Blocks of 0s that have even length

Each chunk is either 1 or 00. Every string in the set is produced as a sequence of chunks.

# Prefix Decomopsitions

$$1^*(01^*)^*, 0^*(10^*)^*$$

are unambiguous, but not block decompo


# Examples:

$$0^*((111)^*(1\cup11)0^*0)^*(\epsilon \cup (111)^* (1 \cup 11))$$

Block decomposition in which each block of 1s has length 1 or 2 (mod 3)


Each block of 1s of even length is followed by a block of 0s of length 1 or 2







