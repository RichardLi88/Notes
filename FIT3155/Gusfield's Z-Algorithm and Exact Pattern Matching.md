## Exact Pattern matching: Introduction
#### The exact pattern matching problem
Given a reference text txt\[1...n] and a pattern pat\[1...m], find ALL occurrences, if any, of pat in txt.
###### Naive Edition
For each letter in txt, start pattern matching with pat. This takes O(mn) time where m = length of txt and n = length of pat

## Gusfield's Z-algorithm 
###### Definition of Z$_{i}$ 
For a string str\[1...n] define Z$_{i}$ ( for each position i > 1 in str) as the length of the longest substring starting at position i of str that matches that matches its prefix
(i.e., str\[i...i+Z$_{1}$ -1] = str\[1...Z$_{1}$])
###### Definition of Z$_{i}$-box
For a string str\[1...n], and for any i > 1 such that Z$_{1}$ > 0, a Z$_{i}$-box is defined as the interval \[i...i+Z$_{i}$-1] of str.
###### Definition of r$_{i}$
For a str\[1...n], and for all i > 1, r$_{i}$ is the right-most endpoint of all Z-boxes that begin at or before position i.
Alterantively, r$_{i}$ is the largest value of j + Z$_{j}$ -1 over all 1 < j <= i, such that Z$_{j}$ > 0.




