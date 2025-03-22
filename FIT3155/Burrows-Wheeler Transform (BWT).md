#Algorithm 

## What is it?
- algorithm to do lossless compression

## BWT definition
- the string formed by letters in the last column (L) of the (sorted) cyclic permutation matrix (M) is the Burrows-Wheeler Transform of the text
- Equivalently, it is also the string formed by the (cyclically) previous letters to the letters in the first column (F)
- Hence if you know the suffix array, you can compute the BWT by subracting 1 from the index

#### Cyclic Permutations
- permutations that are still sorted in the original order, but cycled (e.g. everything shifted to the right wrapped)
#### Matrix general property
- Any k successive columns of the (sorted) cyclic permutation matrix M gives the permutation of all k-mers in S\[1...n]

#### BWT is invertible property
- BWT is invertible
- This implies that we canthrow away the original reference string $S_{1}$ and reconstruct S from BWT(S)
- We will use the notation $BWT^{-1}$ to denote the inverse of a BWT of a string. By inverse it is implied that $BWT^{-1}(BWT(S)) = S$. 


## Clever method to invert using LF-Mapping
- starting point of recovery is always the first letter of BWT.
	- because the next character is always '$' which has lowest ascii value.
- computing the rank of 'x'