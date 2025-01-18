202310281827
Status: #idea
Tags:[[Model Free]]

# Off Policy

1. Behaviour policy that takes actions in an environment
2. Evaluate target policy which updates its V(s)/Q(s,a) but does not samples from its own policy to take actions
3. Advantages:
	1. Experience from past inferior policies
	2. Copy a better agent
	3. (Bellman) Optimal policy does not explore, but we need to explore the environment to know the states and the rewards on it

---
# References

1. https://www.youtube.com/watch?v=0g4j2k_Ggc4