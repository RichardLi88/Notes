#Algorithm 
## Exact Pattern matching: Introduction
#### The exact pattern matching problem
Given a reference text txt\[1...n] and a pattern pat\[1...m], find ALL occurrences, if any, of pat in txt.
###### Naive Edition

^e174d2

For each letter in txt, start pattern matching with pat. This takes O(mn) time where m = length of txt and n = length of pat

# Gusfield's Z-algorithm 

^5194b1

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



## Lab Questions
1. Give an algorithm that takes in two string α and β of lengths m and n, and finds the longest suffix of α that exactly matches a prefix of β. Reason the run-time of your algorithm. 
- have z_box store the longest suffix at position i
- for pattern and text
	- when looking for the longest suffix at position i+1 -> consider the longest suffix at i-1 (let's say length = 5) and check if pattern\[6] == text\[i] if yes then z_box\[i] = z_box\[i-1] + 1

- brute force use standard z_box
- conjecture 1
	- for pattern and text
		- at i, cycle through z_box backwards starting at z_box\[i-1] until z_box\[0] checking at cycle = k if i + z_box\[i-k] -1 == i. If so, return that number

- potential method
- for pattern and text
	- z_box is List\[List\[int]]
	- for z_box, at i, store the length of all suffix's for text\[i] that matches the prefix of pattern (in decreasing length order)
	- for z_box, at i+1, check for all suffix's in z_box\[i] and at j check if text\[i+1] matches pattern\[z_box\[i]\[j]]
	- O(pattern^2)

- for pattern and text
	- suffix_box = List\[int]
	- l,r 
	- while 
	- index at 3 doing explicit matching and get l = 3 r = 9
		- suffix_box\[4] = 4- index
		- suffix_box\[5] = 5 - index
		- suffix_box\[9] = 9 - index etc.
	- if r doesn't traverse through any index, then longest prefix = 0
		




1. Given a string str\[1..n], let len(i) denote the length of the largest suffix of str\[i..n] that is also a prefix of str. Give an algorithm that computes len(i) values. Reason the run-time of your algorithm.