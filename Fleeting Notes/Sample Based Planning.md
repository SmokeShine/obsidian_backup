202311071412
202311071412
Status: #idea
Tags: [[Model]]

# Sample Based Planning

1. Use SARS' combination and sample RS' based on given SA. Instead of tracking V(s) based on probability to move to different S', we sample as if we are interacting with the environment.
	1. Sampling means we are focusing more on events that happen
2. Once we generate samples, we can used [[Model Free]] methods such as Monte Carlo Learning and Q Learning
	1. In experience replay of DQN, we are not focussing on both R and S', but only on S and V(s) to apply iid SGD.
3. As we are approximating R and S', the performance in real world is restricted because of approximation difference
	1. Error compounding 
---
# References

https://www.youtube.com/watch?v=ItMutbeOHtc
