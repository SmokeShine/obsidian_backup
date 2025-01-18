202310282239
Status: #idea
Tags: [[Off Policy]]

# Off Policy Monte Carlo

Need to apply [[Importance Sampling]] for each step in the entire episode

Return weights according to similarity between the target and behaviour policy
1. Does not work in practice
	1. very high variance as target and behaviour policy never match to be useful
		1. Multiplication of two probabilities for the complete episode - very small value
---
# References

1. https://www.youtube.com/watch?v=0g4j2k_Ggc4