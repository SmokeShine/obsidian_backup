202404021522
Status: #idea
Tags: [[Policy Gradients]]

# Natural Policy Gradient

1. Learning rate for policy gradient
	1. clip the gradient to a value
		1. allows reusing samples as there is no sample correlation for estimating gradients
			1. forcing the model to focus on only that one sample. but now due to clipping and Fisher Information Matrix, the gradient update is adaptable, and step size may be different even for the reused sample
	2. large gradients in plateau, small gradients otherwise
	3. restrict [[KL Divergence]] to a value, then calculate policy gradient
2. Inverting Fisher information matrix is expensive
3. No guarantee of reward improvement
4. KL Divergence constraint may not be satisfied due to first order [[Taylor Series]] hack.
---
# References

1. https://freedium.cfd/https://towardsdatascience.com/proximal-policy-optimization-ppo-explained-abed1952457b