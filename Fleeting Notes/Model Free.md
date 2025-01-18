202310261317
Status: #idea
Tags: [[Reinforcement Learning]]

# Model Free

1. Instead of knowing the environment, we can sample one trajectory by allowing agent interacting with the environment
	1. No knowledge of [[MDP]] transitions
	2. No knowledge of [[Markov Reward Process]]
2. When number of states are very high, we can sample one SARS' combination;  


# policy improvement in model free

1. greedy V(s) requires model - Cant do for model free
	1. Need to know all possible transitions that environment may take, and then do a weighted sum
2. greedy Q(s,a) is model free
	1. attempt all actions and the one with maximum Q(s,a) becomes V(s) and new policy

---
# References

1. https://www.youtube.com/watch?v=Nd1-UUMVfz4