202510231308
Status: #idea
Tags: [[AI Engineering]]

# Mixed Precision

- Blackwell GPU can decide precision
	- FP16 for initial layers
		- sensitive to noise
	- FP8 and FP4 for later layers
- Based on heuristic
- Low precision helps with latency and throughput
---
# References

1. https://learning.oreilly.com/library/view/ai-systems-performance/9798341627772/ch02.html#ch02_nvidia_blackwell_dual_die_gpu_1757308026378965