202510271331
Status: #idea
Tags: [[AI Engineering]]

# Magnum IO

- Nvidia
- All GPUs get some portion of data and calculated gradients 
	- do backpropagation
		- dont update local weight
	- all reduce will provide copies of gradients from all other gpus
		- average and update the local weights
		- all models have the same weights now
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
- Congestion algorithms
	- Cubic
	- Round robin
- InfiniBand-level RDMA
	- Two GPUs can access each other memory using network without involving their CPUs
	- So, NIC should be pinned to same NUMA unit as CPU
---
# References

1. https://learning.oreilly.com/library/view/ai-systems-performance/9798341627772/ch04.html