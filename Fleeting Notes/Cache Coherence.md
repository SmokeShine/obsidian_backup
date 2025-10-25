202510231140
Status: #idea
Tags: [[AI Engineering]]

# Cache Coherence

- GPU and CPU share the same memory
	- GRACE CPU and Blackwell GPU
	- Not same memory, but they can access each other's memory
		- to.cuda is required for pytorch but will not trigger copy
	- so there is no need to transfer from CPU to GPU in nvlink
		- so, this can make it look like the GPU has more VRAM than available as it has a space to read and write
			- but this has higher latency
			- this is same as PCIe but nvlink is way faster
- the purpose of CPU is to make sure data processing happens fast enough to saturate GPUs
- NV-HBI - two dies in single chip
	- software thinks there is one big GPU instead of two
		- has to be supported by low level nvidia software
- Can scale upto 72 gbs with the rack
	- NVL72
	- SHARP offloads gradient accumulation so that GPU focus on complex task
- NVL72 can talk to other NVL72 via network
	- have special units so that CPU is not wasting bandwidth on managing network and security
		- this network is called infiband switches
	- multi rack is called "AI Factory"
---
# References

1. https://learning.oreilly.com/library/view/ai-systems-performance/9798341627772/ch02.html