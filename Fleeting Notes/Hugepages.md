202510241139
Status: #idea
Tags: [[AI Engineering]]
 
# Hugepages

- can be used to increase size of TLB 
	- rows will remain same, width will increase
	- small width is efficient when we don't know the workload and the memory access could be both small and large
	- but for data processing, it can become million of small huge pages
		- it will be large and hence increasing hugepages is preferred
			- disable it during inference
	- 
---
# References

1. https://learning.oreilly.com/library/view/ai-systems-performance/9798341627772/ch03.html#ch03_transparent_hugepages_1757308027909872