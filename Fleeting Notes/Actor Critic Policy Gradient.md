202310311537
Status: #idea
Tags: [[Policy Gradients]]

# Actor Critic Policy Gradient

Similar to [[Monte Carlo Policy Gradient]] and [[REINFORCE]] but uses estimate instead of full trajectory returns.
 - so, we can use [[TD(lambda)]] to update actor-critic after each step
 - So, we have small variance as each action has immediate impact, rather than waiting for the whole episode to end, and then it becomes difficult to attribute which action lead to the change
	 - because of approximate value from target, bias would be high


1. Critic to estimate Q(s,a) for a policy
	1. Policy evaluation
	2. Update critic using eligibility traces from [[Temporal Difference Learning]] - TD0
2. Action - update theta to improve policy in the direction suggestion by critic
---
# References

1. https://www.youtube.com/watch?v=KHZVXao4qXs