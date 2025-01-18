202310261326
Status: #idea
Tags: [[Model Free]]

# Temporal Difference Learning

1. Can learn from episodes without termination
2. Take a sample from the trajectory and estimates how much return was possible if complete trajectory was followed 
	1. TD Target - Take actual return that was possible to get in [[Monte Carlo Learning]] and replace with immediate [[Reward]] + gamma * state value function of next state
		1. Biased estimate of state value function
	![[Pasted image 20231026142855.png]]
	2. Can be used for sparse rewards. Eg travel time will increase if it starts raining. MC wont adjust as it will wait for end of journey, while TD will adjust
		1. So lower variance
---
# References

1. https://www.youtube.com/watch?v=PnHCvfgC_ZA