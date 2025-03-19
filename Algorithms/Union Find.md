#Algorithm 
## Find 
- the function of the find algorithm is to find the root node
```python
def find(i):
	if parent[i] == i:
		return i
	else:
		return find(parent[i])
	
```
- returns itself if it is the parent
- else recursively finds the parent node
- this can have a worst case time of O(n)

## Union
- function is to join two different sets together
```python
def union(n1,n2):
	root_n1 = find(n1)
	root_n2 = find(n2)
	if root_n1 != root_n2:
		parent[root_n2] = root_n1
```
- this can have a worst case time of O(n)


## Optimising by Path compression
```python 
def find(i):
	if i == parent[i]:
		return i
	else:
		parent[i] = find(parent[i])
	return parent[i]
```
- path compression, sets every child that is not its own parent to be the direct child of the parent.

## Optimising by Union by rank
- Union by rank joins the tree with the smaller rank to the tree with the bigger rank
- The rank tracks the upper bound for the height of the tree.
- Worst case by optmising for using union by rank for m operations is m log (n) where n is the number of total nodes
```python
parent[1...n] = [1...n]
rank[1...n] = [0] * n

def union(n1,n2):
	root_n1 = find(n1)
	root_n2 = find(n2)

	if rank[root_n1] < rank[root_n2]:
		parent[root_n1] = root_n2
	else:
		parent[root_n2] = root_n1
		if rank[root_n1] == rank[root_n2]:
			rank[root_n1] += 1
```





