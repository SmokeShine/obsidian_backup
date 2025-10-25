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
	- useful for 1 GPU and not a cluster
---
# References

1. https://learning.oreilly.com/library/view/ai-systems-performance/9798341627772/ch02.html#ch02_nvidia_blackwell_dual_die_gpu_1757308026378965