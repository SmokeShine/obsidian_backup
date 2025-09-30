202311011709
Status: #idea
Tags: [[Actor Critic Policy Gradient]]

# Advantage Function

1. For reducing variance without changing expectation
2. Subtract a baseline function
	1. Good baseline is V(s), so advantage function would become Q(s,a)-V(s)
		1. So, critic needs to learn parameters for both V(s) and Q(s,a)
		2. this also mean, that we need to take an action which is better than policy default action V(s)
			1. V(s) is average of all Q(s,a)
	2. Another baseline is TD error (V(s)), so we need to learn parameters only for V(s)
---
# References

1. https://www.youtube.com/watch?v=KHZVXao4qXs