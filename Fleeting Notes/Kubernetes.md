202510262146
Status: #idea
Tags: [[AI Engineering]]

# Kubernetes

- This is similar to [[MCP]] how tools are exposed and discovered
	- GPU exposes their config to resource manager
	- Kubernetes wont know about NUMA nodes if all GPUs allocated are in the same node and this can be issue
		- There is no topology aware scheduling even though Kubernetes Topology Manager is aware of location
		- Reserve the entire node at a time to fix this
			- But if we use MIG to virtually partition in the GPU, if all requested GPUs by Kubernetes dont belong to same NUMA node, it will go into pending even though combined GPUs across NUMA nodes were available
- This is preferred for inference while [[SLURM]] is preferred for training
- If a pod uses too much memory, swapping to disk is possible and this can cause jitter during inference
- When two jobs are running in same pod (one analytics and another e commerce front end), the I/O from analytics can make everything slow
	- So, we throttle analytics workload such that bytes/second I/O operation are slower which in turn will make the scheduler priortise the ecommerce queue frequently
		- it is not FIFO
---
# References

1. https://learning.oreilly.com/library/view/ai-systems-performance/9798341627772/ch03.html#ch03_orchestrating_containers_with_kubernetes_topology_1757308027910741