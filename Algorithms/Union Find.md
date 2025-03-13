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

```