202503121338
Status: #idea
Tags: [[Proximal Policy Optimization (PPO)]]

# Generalized Advantage Estimation (GAE)

- A good action can be followed by bad action
	- so reward should have been good but was not, because of future actions
	- This cause high variance
- [[Critic]] tries to average all trajectories and give a single value


---
# References

1. https://arxiv.org/pdf/2402.03300
2. https://www.reddit.com/r/reinforcementlearning/comments/kjxrpk/generalised_advantage_estimator_gae_how_does_it/