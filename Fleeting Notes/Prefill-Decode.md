202510291148
Status: #idea
Tags: [[AI Engineering]]

# Prefill-Decode

- Model is in harddisk
	- it is read by CPU and pushed to GPU HBM
- For the input prompt, it passes through the network and calculates the KV cache
	- The KV cache is also dumped on GPU HBM
- During decode, KV cache and model are loaded again from HBM and autoregressively decode the next token
	- if there is disaggregation, we need to pass the KV cache through the network to the inference GPU using NIXL
		- So, while KV cache is getting processed, we can use the partial KV cache received to start calculation for next token
---
# References

1. https://learning.oreilly.com/library/view/ai-systems-performance/9798341627772/ch04.html#ch04_in_network_sharp_aggregation_1757308031866835