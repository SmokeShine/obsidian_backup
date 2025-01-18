202310281830
Status: #idea
Tags: [[On Policy]]

# On Policy Temporal Difference Learning

1. Replace MC from [[On Policy Monte Carlo]] in policy evaluation to [[Temporal Difference Learning]] and update Q(s,a)
2. SARS'A  - For a state, take an action, collect reward and new state from environment, then sample our policy to get the new action for new state
	1. As TD can use partial trajectories, we use estimate of return
		1. can update the policy every time step
3. Step size for decay required for convergence is Robbins-Monro sequence 
![[Pasted image 20231028204932.png]]
---
# References

1. https://www.youtube.com/watch?v=0g4j2k_Ggc4