202510252325
Status: #idea
Tags:

# Depth First Search

- Clone tree
	- deepcopy requires additional memory similar to windows
		- so, for each node, we need to save its children in the dictionary
		- the dictionary is huge, and there is not easier way
			- cant use set as it is undirected graph and loops are possible
- Course Sequence
	- First create an adjacency list
	- Then use DPS
		- This is same as linked list search to find loop
			- but we cant use hare and tortoise as it is not a tree with left and right
				- can have multiple dependencies
- Course Sequence 2
	- Topological Sort
- Max Area of Island
	- DFS and seen
		- Add to stack only if it is within the boundary
			- Four directions
				- Can be put in loop
- Longest Increasing Path in Matrix
	- 
---
# References

1. 