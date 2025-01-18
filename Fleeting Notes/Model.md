202310232357
Status: #idea
Tags: [[Agent]]

# Model

Learn the environment [[MDP]] model to plan and improve value/policy. 
1. If value function changes drastically on an iteration, that means policy also changed drastically
	1. so it is difficult to learn V(s) and may be easier to learn the model
2. sparse reward - it will be 0 unless the win/loss position in chess
	1. so very hard to be model free

Predict how the environment will respond to an action. 
1. Transitions: predict what will be the next state given by the environment
2. Rewards: predict what will be the next reward given by the environment

In Model free, we learn only from real experience. But in model, we learn from simulated experience/samples - we can learn a supervised model to predict R and S', and using this we can create more samples.



---
# References

1. https://www.youtube.com/watch?v=2pWv7GOvuf0
2. https://www.youtube.com/watch?v=ItMutbeOHtc