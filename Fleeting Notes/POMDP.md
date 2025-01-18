202310232316
Status: #idea
Tags: [[MDP]]

# POMDP
Partially observable MDP. 
1. We need to build the agent state instead of directly using the environment state as we did in [[MDP]]
2. As we don't know the environment state, we are create a probability distribution vector denoting where the agent may be in the environment state. This can be used to decide which action to take next
3. instead of dealing with probability vector, we can use a RNN that takes input as current observation and previous state to output the next state
---
# References

1. https://www.youtube.com/watch?v=2pWv7GOvuf0