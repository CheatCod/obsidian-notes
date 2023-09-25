
# Pattern Matching

- Search for a string (pattern) in a large body of text
- $T[0..n-1]$ - the text being searched within
- $P[0..m-1]$ the pattern being searched for
- Return the first $i$ such $P$ is the first occurance in $T$
- If $P$ does not occur in $T$, return fail

**Final exam questions:**
Lec 18
- Define the KMP failure funtion
- Construct the KMP failure array

Lec 19
- Boyer-Moure : Suffix Skip Array (shift to right)
- Last-occurance (bad character) heuristic


## General Idea of Algorithms

Pattern matching algorithms consit of guesses and chekcs
- A guess is a position $i$ such that $P$ might start at $T[i]$
- A check of a guess is a single position $j$. We must perform $m$ guesses to check a correct answer.

## KMP Algorithm

- Compares the pattern to the text in **left-to-right**
- **Shifts** the pattern more intelligently than the brute-force algorithm 
- When a mismatch occurs, what is the most we can shift the pattern (reusing knowledge from previous matches)

Claim: max shift possible after a mismatch (at position $0 \le j \le m-1$):

length of the largest prefix of $P[0..j]$ which is a suffix $P[1..j]$

- $i$ : index in $T$ (*shift is not here*)
- $j$ : index in $P$ (*shift is here*)

In the algorithm on slide 10, $I$ gets incremented each time through the loop, $j$ get shifted based on matches vs mismatches, goal here is to pick the optimal shift based on a mismatch of $j$, so that characters already matched don't need to be rechcked. We start from the first char not yet matched

## KMP Failure Array
- Preprocess the **pattern** to find matches of prefixes of the pattern with the pattern itself
- The **failure array** $F$ of size $m$: $F[j]$ is defined as the length of the largest prefix of $P[0..j]$ that is also a suffix of $P[1..j]$
- $F[0] = 0$
- If a mismatch occurs at $P[j] \neq T[i]$ we set $j \leftarrow F[j-1]$
- 