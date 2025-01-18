202501141524
Status: #idea
Tags:

# Vector-Quantized Variation Autoencoder (VQ-VAE)

1. Describing an image in text, is converting continuous representation to discrete token from dictionary
	1. Quanitization of continuous number creates a codebook for each quantile
	2. Use image to get [[Posterior]] and we do not have a simple [[Prior]]
		1. It is completely deterministic and has no sampling or prior
	3. We have a [[Codebook]] and the latent vector will be assigned to the nearest value from the codebook
2. the codebook assigns latent vector from prior a specific vector with probability 1.
	1. for training, instead we use uniform = 1/codebook len, such that we can now sample from this uniform distribution
		1. after training, there may be dependence of one vector with another in the codebook
			1. similar to words having relation with each other in sentence
	2. [[KL Divergence]] of posterior with prior is a constant (log K) and hence the derivative of it will not come in loss function
3. Sample code words from this codebook to generate the image
	1. we started with image, learnt a discrete deterministic prior
	2. now we can sample from this code book to generate images
		1. sample 1st value for pixel 1
		2. decode after sampling
		3. now for pixel 2, condition it on the first sample and run it autoregressively
4. Quantization is not differentiable so simply copy the gradients from decoder to encoder. This is called [[Straight Through Estimation]]
5. For the loss, we use [[Stop Gradient]] which makes gradient 0 during [[backpropogation]]. This is useful when we want to improve only one node type
	1. Do it for codebook once
	2. Do it for encoder weights once
		1. both vectors could fluctuate a lot if done together
			1. unstable training
			2. redundant codewords in the codebook
	3. In this way, we try to move them close to each other
		1. Improves stability of training
		2. Weights do not become very large
---
# References

1. https://www.youtube.com/watch?v=yQvELPjmyn0

