202510061621
Status: #idea
Tags:

# Algorithms

- Array - O(1) lookup if index is known but difficult to insert
- Linked List - O(n) search but easier to insert at head
- Double Linked List - Tries to reduce lookup with tail
- Circular Queue - Adds head and end pointer to array, insertion is still expensive if new array needs to be created
- Deque - can be circular queue / double linked list as both have head/tail pointers
- Stack - Can be dequeue
- Queue - Can be dequeue
- Heap - only pop matters, so can be array
	- Add element at end and bubble up
	- Add last element as root on pop and bubble down
- Binary Search Tree
	- deletion can cause memory waste due to fragmentation
		- imbalance, so it is linked list
	- Not self balancing
	- Add element at end
		- left/right comparison
- Tree Heap - Adds priority
- Random Search Tree -  Add random priority
- AVL Tree - Can self balance binary search tree with AVL rotations and assumptions on height and root
	- Good for search
- Red Black Tree - Can self balance with AVL rotations and assumptions on height and root
	- Good for insertion
- KD tree 
	- (K - D)imensional 
		- Split by each axis similar to how we do with random forest
	- nearest neighbour but can require more processing as nearest neighbour could be in another branch
- B- tree -  if BST grows, then it can be dumped on disk
	- very fast read
	- self balancing
		- because all leafs are at same depth
			- split if depth changes and add to root instead
	- memory aware
	- each node contains full data
		- traversing is slow
			- caching is difficult
	- select all * in query will take a lot of time
- B+ tree
	- each node contains only key
		- Easier to cache as smaller keys will be close to each other in memory
	- all data is on leaves - create a pointer from each leaf to another like a linked list for O(n) time
		- So, we returned to linked list but with the ability to cache keys
			- the internal nodes helps in balancing which nodes should grow
				- but leaf data can now move around
					- leaf is still linked list node and swapping can fix it quickly
		- It is no more a tree but a DAG
- Graph 
	- No parent/child
	- Does not need to be connected
	- Edge 
		- Can have direction
			- Can have cycles
		- Can have weights
	- BFS takes more memory in queue if breadth is large
	- DFS does not guarantee shortest path between nodes
- Djikstra 
	- Similar to BFS but with weights
		- prioritise smallest sum
			- so, the queue is a priority queue
				- Instead of storing complete path and sum, we store the last node and sum
			- in BFS, one node can be visited only once, in dijkstra, one node can be visited multiple times
- Minimum spanning tree
	- Prim
		- Uses priority queue like dijkstra
			- Can work with negative edges
	- Kruskal
		- Uses priority queue like dijksta
- Disjoint set
	- Check if two points are connected or not
		- BFS and DFS are not fast enough if we have do this for a lot of points in a big network
			- query cost is too high like in prefix sum
		- find(start) and find(end) - if they return the same set, they are connected
	- Uses up-tree data structure along with path compression
---
# References

1. https://stepik.org/lesson/28947/step/4?unit=9959