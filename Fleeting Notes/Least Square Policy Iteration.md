202310311212
Status: #idea
Tags: [[Deep Q-Network(DQN)]]

# Least Square Policy Iteration

1. Least squares Q-learning for policy iteration
2. Greedy policy improvement (not epsilon greedy)
3. Need to invert Matrix
	4. Solve for Expectation of change in weight=0 and invert for finding w
		1. Assume we have an oracle that gives the value of V(s) to find the difference
	5. Can use Shermann Morrison Algorithm for Improved runtime
---
# References

1. https://www.youtube.com/watch?v=UoPei5o4fps