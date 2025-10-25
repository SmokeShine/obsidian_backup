202510231312
Status: #idea
Tags:[[AI Engineering]]

# GPU

- GPU has streaming processors, which is like cores
	- contains maths, tensor operation units
	- Each SP has warps
		- warps are threads in parallel
- Persistence mode - if gpu goes to sleep, it will take some time to take up the work again
	- when enabled, the gpu does not go to sleep
- MIP
	- Can split GPU into virtual GPUs
		- cant use nvlink anymore
		- will show as separate GPU in nvidia-smi
	- useful for 1 GPU and not a cluster
- Can undervolt to reduce heat
	- useful for long running jobs
		- thermal throttling can kick in otherwise
- To avoid fragmentation, pytorch does not return allocated memory for some time
- in blackwell, GPU to CPU RAM swapping is possible
	- Slow
	- But if CPU RAM had already swapped to disk, this will be extremely slow, instead of just slow
- When using docker, the cuda inside the docker should support the driver in the host
	- everything is passthrough when using GPU
- 
---
# References

1. https://learning.oreilly.com/library/view/ai-systems-performance/9798341627772/ch02.html#ch02_nvidia_blackwell_dual_die_gpu_1757308026378965