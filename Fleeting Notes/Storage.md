202510311120
Status: #idea
Tags:

# Storage
- For multi system training, reading from one single source can become a bottleneck due to read operations
	- We can change read size and write size
- if GPU can directly access storage instead of via CPU, then it will speed up
	- ML uses shuffling data for training
		- Read head has speed and can read some more memory address, it will help in sequential 
		- but for random access, this will slow down
			- caching memory assuming data will be reused is wasted
---
# References

1. https://learning.oreilly.com/library/view/ai-systems-performance/9798341627772/ch05.html#ch05_distributed_parallel_filesystems_and_object_stor_1757308032401611