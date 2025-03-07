## Exact Pattern matching: Introduction
#### The exact pattern matching problem
Given a reference text txt\[1...n] and a pattern pat\[1...m], find ALL occurrences, if any, of pat in txt.
###### Naive Edition
For each letter in txt, start pattern matching with pat. This takes O(mn) time where m = length of txt and n = length of pat

# Gusfield's Z-algorithm 
###### Definition of Z$_{i}$ 
For a string str\[1...n] define Z$_{i}$ ( for each position i > 1 in str) as the length of the longest substring starting at position i of str that matches that matches its prefix
(i.e., str\[i...i+Z$_{1}$ -1] = str\[1...Z$_{1}$])
###### Definition of Z$_{i}$-box
For a string str\[1...n], and for any i > 1 such that Z$_{i}$ > 0, a Z$_{i}$-box is defined as the interval \[i...i+Z$_{i}$-1] of str.
###### Definition of r$_{i}$
For a str\[1...n], and for all i > 1, r$_{i}$ is the right-most endpoint of all Z-boxes that begin at or before position i.
Alterantively, r$_{i}$ is the largest value of j + Z$_{j}$ -1 over all 1 < j <= i, such that Z$_{j}$ > 0.

###### Definition of l$_{i}$ 
For a string str\[1...n], and for all i > 1, l$_{i}$ is the left end ofthe Z-box that ends at r$_{i}$. In case there are multiple, l$_{i}$ will be the left end of any of those Z-boxes.

#### Main point of Gusfield's Z-algorithm!
- Naive computation of these values, given some string str\[1...n] would require O($n^{2}$)-time.
- Gusfield's Z-algorithm allows computation of these values, in O($n$)-time
#### Base case
Compute Z$_2$ by explicit left-to-right comparison of characters str\[2...] with str\[1...] until a mismatch is found.
If Z$_{2}$ > 0
- set $r$(i.e., $r_{2}$) to 2 +Z$_{2}$ + 1 = Z$_{2}$ + 1 (start_point + len + 1)
- set $l$ (i.e., $l_{2}$) to 2
else (if Z$_{2}$ == 0)
- set $r$ (i.e.,r$_{2}$) to 0
- set $l$ (i.e., l$_{2}$) to 0

## Preprocessing (of Z$_i$ values) for str\[$1...n$] takes O($n$) time
- Total time is directory proportional to the sum of:
	- the number of iterations
	- the number of explicit character comparisons
- the preprocessing has n-1 iterations
- Any iteratiion that explicitly performs comparisons ends as soon as a mismatch occurs, hence there are at most n - 1 mismatches
- the number of matches (performed explicity) is at most n, because:
	- r$_{k}$ >= r$_{k-1}$ (for all iterations)
	



