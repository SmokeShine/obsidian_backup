202509300724
Status: #idea
Tags: [[Algorithms]]

# Circular Arrays

- Double Linked list allows adding elements in O(1) on both ends
- Array allows O(1) lookup based on base address
- Circular queue has pointers for both start and end on a circular array
- Once filled, new circular queue is added
	- for O(1) access, we take % of circular queue length to find the backing array 
	- there is no O(1) search, it will still be binary search
---
# References

1. https://stepik.org/lesson/28869/step/1?unit=9906