202408271232
Status: #idea
Tags: [[Advantage Function]]

# Rollout Baseline

- if used a [[Rollout Policy]] n times and received different rewards, we take the average, and compare against individual run, so it is a measure of variance
- in [[Advantage Function]], we compare the reward for taking the action against the default reward (V(s)). So, it is a little different. 
- Baseline can be any random variable, but its value should not change based on action taken
	- so using a frozen network or static value is fine
---
# References

1. 