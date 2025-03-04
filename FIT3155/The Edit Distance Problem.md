## Definition
The edit distance problem is a way to formally classify how similar or dissimilar two strings of text are. For example, the words “computer” and “commuter” are similar, as we can change one into the other by just modifying one letter, ‘p’ to ‘m.’ The words “sport” and “sort” are similar, as one can be changed into the other by deleting one letter from the first (or equivalently, inserting a new letter into the second).

There are three operations that can be done to modify one string into another:
1. Insert a new symbol anywhere in the string. 
2. Delete one of the symbols from the string. 
3. Replace one of the symbols in the string with any other symbol.

We can define the sub-problem to be:
$$
	Dist[i,j] = \{\text{The edit distance between the prefixes} S_{1}[1...i]\text{ and } S_{2}[1...j]\}
$$
