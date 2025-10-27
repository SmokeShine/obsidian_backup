202510271707
Status: #idea
Tags:

# DistributedDataParallel

- Suppose we have 3 GPUs. Each GPU will have different gradients based on layer number
	- when we call all reduce, it is similar to collect and will trigger all gradients for the same layer in one location, to get the average required for backpropagation
	- as we know the order of backpropagation is reverse, we can start this accumulation process for last layers before waiting for the complete backpropagation to reach layer 1
		- so, when bp is at layer 2, we already collected gradient average from layer 3
	- avoid synchronization by using .item as it will push the data to cpu and async advantage will be lost

---
# References

1. https://learning.oreilly.com/library/view/ai-systems-performance/9798341627772/ch04.html#ch04_reducing_communication_frequency_and_volume_1757308031865288