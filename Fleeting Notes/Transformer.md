202403211422
Status: #idea
Tags: 

# Transformer

1. Encoder
	1. Input 
		1. Positional Embedding
			2. Geometric progression from $2 \pi$ to $10000.2\pi$ 
			3. Sin
			4. Cos
		3. Input Embedding
	2. Sublayer
		1. Multi head attention
			1. Concatenate output from each attention head
		2. Fully Connected Feedforward
	3. Layer Normalization
		1. Add & norm
	4. Residual connection from input to output of each sublayer
	5. Can be parallelized for training
2. Attention - helps in finding information in smaller resolution
	1. Multiple heads to increase resolution
	2. Self Attention
		1. Scaled dot product
			1. key
			2. value
			3. query
		2. query is item to be search, while key-value is like a table
			1. $(QK/scaling factor)V$
			2. scaling factor is required as for large size of $Q$ and $K$ , gradients are very very small without it
	3. Cross Attention
		1. Uses output to create query, and use output from encoder as key-value
4. Decoder
	1. Input
		1. Output embedding
		2. Positional Embedding, shifted so that future ones are masked
	2. Sublayer
		1. Multi head attention
		2. Cross attention using output of encoder
		3. Full Connected Feedforward
5. Adam optimizer
	1. Warm start where learning rate is high and gradually reduces after warm start
6. Can be parallelized for encoding
7. Long term dependency
8. same compute
---
# References

1. https://arxiv.org/pdf/1706.03762.pdf