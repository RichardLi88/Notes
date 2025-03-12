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
Extra:
[[#^1b575a|Galil's Optimisation]]
[[#^1a8347|Summary]]


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
- If $k-R(x)$ < 0, that is that $R(x) > k$, then we can only shift by 1 position
- 

### Good suffix shift rule

^577620
Definition 1: $Z_{i}^{suffix}$
Given **pat\[1...m]** define $Z_{i}^{suffix}$ for $i < m$, as the length of the longest substring ending at position i of **pat** that matches its suffix, i.e. **pat\[i-$Z_{i}^{suffix}$] = pat\[m - $Z_{i}^{suffix}$ + 1...m]**
- Using the z-algorithm but manipulating it to store the greatest substring that matches up to point $x$.

Definition 2: Matched Prefix
The matched prefix value $mp(k+1)$, associated with the suffix $\textbf {pat} [k+1...m]$ is defined to be the largest suffix of $\textbf {pat}[k+1...m]$ that matches the prefix $\textbf {pat} [1...m-k]$.

### Galil's optimisation

Consider some general iteration where pat\[1...m] is being compared with txt\[j...j+m-1] via a right-to-left scna. Assum that the pattern matches the text down to some position k + 1,
$$
pat[k+1...m] = txt[j+k...j+m-1]
$$
and the iteration is then ended due to a mismatch at position k, or because an occurrence of the pattern was found. Assume the pattern is shifted to the right with respect to the text using the good suffix rule and that gs(k+1) = p.

If p > 0, then,
$$
pat[p-m+k+1....p] = txt[j+k...j+m-1]
$$
and we can skip making comparisons in this region in the right-to-left scan in the next iteration.


### Summary of Boyer-Moore's Algorithm

Given inputs pat\[1...m] and txt\[1...m] begin by aligning pat\[1...m] with txt\[1...m]. The algorithm proceeds as follows:
- Compare the current alignment in a right-to-left scan, applying Galil's optimisation to terminate the scan prematurely if appropriate.
- After the scan has terminated due to a mismatch, or an occurrence of the pattern ebing found
	- use the (extended) bad character rule to determine how many places to the right pat should be shifted under txt. Call this amount n$_{bad character}$.
	- Use the good suffix and the matched prefix rules to determine how many places to the right pat should be shifted under txt. Call this amount n$_{goodsuffix}$.
- Shift pat to the right under txt by max($n_{badcharacter}$, $n_{goodsuffix}$)
- 

^1a8347
