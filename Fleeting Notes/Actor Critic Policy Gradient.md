202310311537
Status: #idea
Tags: [[Policy Gradients]]

# Actor Critic Policy Gradient

Similar to [[Monte Carlo Policy Gradient]] and [[REINFORCE]] but uses estimate instead of full trajectory returns.

1. Critic to estimate Q(s,a) for a policy
	1. Policy evaluation
	2. Update critic using eligibility traces from [[Temporal Difference Learning]] - TD0
2. Action - update theta to improve policy in the direction suggestion by critic
---
# References

1. https://www.youtube.com/watch?v=KHZVXao4qXs