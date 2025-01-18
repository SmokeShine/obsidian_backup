202310301450
Status: #idea
Tags:[[Value Function Approximations]]

# Incremental Prediction Algorithms

1. For calculating gradient of weight, in RMSE, we need labels for V(s). As we don't have labels in RL, we use estimate
	1. [[Monte Carlo Learning]] - real return 
	2. [[Temporal Difference Learning]] - use TD target = reward + estimate of return 
	3. [[TD(lambda)]] - lambda return = combination of Monte Carlo learning and TD by using compounding lambda

Noisy oracle

2. Once we have the weights, we can calculate v(s) for a state. Act [[Epsilon Greedy Exploration]] on it.
3. But in model free, we need to get q(s,a) and not v(s), and then act epsilon greedily - Value function approximator
---
# References

1. https://www.youtube.com/watch?v=UoPei5o4fps