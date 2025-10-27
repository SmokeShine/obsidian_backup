202510271331
Status: #idea
Tags: [[AI Engineering]]

# Magnum IO

- Nvidia
- Contains communication libraries
	- Training
		- NCCL
		- GPUDirect RDMA
		- GDS
	- Inference
		- NIXL
			- Disaggregated
- Similar to how pipelining is done, we need to make data through network faster 
	- break gradients into small buffers instead of waiting for whole buffer to fill
	- compress
- DistributedDataParallel
	- Fills the gradient bucket and then give it to communication layer in async
---
# References

1. https://learning.oreilly.com/library/view/ai-systems-performance/9798341627772/ch04.html