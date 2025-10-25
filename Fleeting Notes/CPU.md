202510231653
Status: #idea
Tags: [[AI Engineering]]

# CPU

- CPU is responsible for reading data of the disk, creating tokens and then creating GPU kernels. It is then passed to OS scheduler
	- So, if this is slow, GPU is not fed with useful work 
- Numa - each CPU has a dram
	- if CPU core has to use numa from another core, it will be  slow
		- [[Cache Coherence]] will reduce latency but it is better to design it correctly than relying on cache coherence
---
# References

1. https://learning.oreilly.com/library/view/ai-systems-performance/9798341627772/ch03.html#ch03_pytorch_and_higher_level_ai_frameworks_1757308027909643