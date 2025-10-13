202509300743
Status: #idea
Tags: [[Algorithms]]

# Min Heap

- Queue is FIFO, Stack is LIFO. There is no way to rearrange if a high priority item comes in
- Heap property - all children should have lower priority than root
	- Should be [[Binary Tree]] with 0/1/2 children
	- [[Complete Binary Tree]] - left to right filled and all prior levels are filled
		- This is required while insertion as put the new node on the last open slot and bubble up comparing with root
			- Worst case O(n) if it looks like a linked list, but it is complete, so max height is log N
				- O(log N)
		- Removal -  from the top
			- take the last slot and put it as root and trickle down
			- O(log N)
- Stored in array
	- Root and child relation defined by equations
		- Root is 0,3,5 -  2^L -1
			- Left  = 2 (2^L -1) + 1
			- Right = 2 (2^L -1) +2 
---
# References

1. https://stepik.org/lesson/28863/step/7?unit=9900