202311081125
Status: #idea
Tags: [[Forward Search]]

# Monte Carlo Tree Search

State of the art

1. Simulation policy - how we choose action on simulated states
2. Simulate 100 episodes take average of return
	1. if action is taken into account, it because Q(s,a)
3. For subsequent states, we can calculate Q(s,a) by taking mean of all possible trajectories through that node, and not only the sampled trajectory
4. Simulation policy improves
	1. Pick action with max Q(s,a) 
		1. if state not in tree, pick action randomly
		2. When Simulation is running, for known cases it picks the optimal action and returning random otherwise
5. Monto Carlo Evaluation + epsilon greedy

---
# References

1. https://www.youtube.com/watch?v=ItMutbeOHtc