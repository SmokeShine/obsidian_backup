202510271427
Status: #idea
Tags: [[AI Engineering]]

# gradient check

- There are activations and there are learnable weights
- activations are output from each node during forward pass
	- gradient checkpoints simply do not save the computation of activations in the computation graph for each sample
		- save only selected activations
		- this saves memory
---
# References

1. https://residentmario.github.io/pytorch-training-performance-guide/gradient-checkpoints.html