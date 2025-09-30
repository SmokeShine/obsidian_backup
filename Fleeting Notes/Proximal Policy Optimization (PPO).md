202403111133
Status: #idea
Tags: [[Actor Critic Policy Gradient]]

# Proximal Policy Optimization (PPO)

proximal - updates very near 

1. Very similar to [[REINFORCE]]
2. Increase the penalty every time, the [[KL Divergence]] is too large
	1. large divergence, large updates, unstable policy
		2. overshoots rewards peak
3. Divergence cap is difficult even for same problem, so PPO uses a target divergence so that the update is large enough to change the policy and small enough for stability.
	1. meaningful update without excessive drift
4. PPO Penalty
5. PPO Clip

![[Pasted image 20250312133549.png]]
---
# References

1. https://towardsdatascience.com/proximal-policy-optimization-ppo-explained-abed1952457b
2. https://freedium.cfd/https://towardsdatascience.com/proximal-policy-optimization-ppo-explained-abed1952457b
