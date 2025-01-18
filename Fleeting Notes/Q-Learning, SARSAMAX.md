202310282248
Status: #idea
Tags: [[Off Policy]]

# Q-Learning

1. Same as [[Off Policy TD]] but we don't need [[Importance Sampling]] 
2. [[SARSA(lambda)]] with lambda = 0 
3. Directly update Q values of target policy by taking action from behaviour policy
	1. this denotes what is the real value of taking the action in target policy
 
SARSAMAX
6. Target policy is greedy
7. Behaviour policy is [[Epsilon Greedy Exploration]]
 ![[Pasted image 20231028225956.png]]
---
# References

1. https://www.youtube.com/watch?v=0g4j2k_Ggc4