#Algorithm 
- both [[#^03a5cf|Boyer-Moore]] and [KMP] algorithms are linear time methods and have a worst case complexity of O(m+n), assuming a pattern and text of length m and n respectively.
- However Boyer-Moore can run sublinear time on average
- KMP can be more generalised for more complex pattern matching problems that is not amenable for [[Gusfield's Z-Algorithm and Exact Pattern Matching#^5194b1|Z-Algorithm]]

## The Boyer-Moore Algorithm

^03a5cf
- Similar to the [[Gusfield's Z-Algorithm and Exact Pattern Matching#^e174d2|naive method]] aligns the pattern with the text and checks for a complete match in each alignment
- to improve on the naive method, the Boyer-Moore incorporates three clever ideas:
	- [[#^8dbd74|Right-to-left Scanning]]
	- [[#^fa17c9|Bad Character shift rule]]
	- [[#^577620|Good suffix shift rule]]

### Right-to-left Scanning

^8dbd74
- for a given alignment between the pattern and the text, it begins by comparing pat\[end] with txt\[i] and so on, moving through the text from the start but looking for matches to the end of the pat.
- this right-to-left scan offers no performance benefit alone
### Bad Character shift rule

^fa17c9
- We want to store the position of the right most occurrence of x in the pattern
- Algorithmically, 
$$

R(x)  = 
\begin{cases}
\text{Position of rightmost occurrence of x in the pattern } \qquad \text{if x occurs in pattern,}\\
0 \hspace{11.4cm} \text{otherwise}\\
\end{cases}
$$
- If there is a mismatch, shift the pattern to align with the bad character by $k - R(x)$ places to the right, so the rightmost occurence of x aligns with the mismatched character to ensure it matches
- If the rightmost occurence of $x$ is 0, there has been no matches so far, then it is safe to shift the whole pattern past the occurrence of x in the text.
- Only use this when $R(x)  < k$, if this is not the case then the bad character rule cannot be used.

### Good suffix shift rule

^577620

