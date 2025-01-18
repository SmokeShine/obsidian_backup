202310232224
Status: #idea
Tags: [[Model Free]]

# Monte Carlo Learning

1. Takes a trajectory and returns state value function from the intermediate rewards
2. Assumes termination of episode
3. [[Value Function]] is expected future return from a state. In MC, we replace expected return (using probability) to simple average of seeing the return at that state.
4. First Visit Monte Carlo - use only the first appearance in an episode to increase the counter. Ignore multiple appearances
5. Every Visit Monte Carlo - count everything, even if there is a loop.
6. Only state visited by the agent matters. So, we need to use [[Explore Exploit]] to find all states reachable by the agent.
7. With enough samples for a state, we can use [[Central limit theorem]] to approximate the mean value of population.
	1. For non stationary (environment from the past changed now), take mean from last n occurrences, running mean.
		1. We can use a multiplier to adjust the current mean based on seeing the new value
---
# References

1. https://www.youtube.com/watch?v=PnHCvfgC_ZA