202310251201
Status: #book
Tags:

# Glossary of RL

# Agent

1. Policy: Given a state, what action to take
2. Value Function: Decide which state is good
3. Model: Approximation how the environment works from the eyes of agent
4. Based on the combination of above three, agent could be 
	1. value based, policy based or actor critic
	2. model based or be model free

# Bandit

1. MDP with one state
2. Choose one state and episode ends
# Bellman Expectation Equation for MRP

1. ties current Reward with future Return in Markov Reward Process

![[Pasted image 20231024154929.png]]

2. take an action to get a good reward to end up in another state, but is the next state worth going? So based on immediate reward and future returns, what is the value of the "original" state?
3. Can be solved by inverting the matrix, Dynamic Programming, Monte-Carlo Evaluation, Temporal-Difference Learning

# Bellman Optimality Equation

optimal value function - agent can take the action with the max Q-value on that state instead of taking expectation.

optimal state-value function - As we can't control where the environment pushes us after taking the action, there is no max here, but we need to take expectation of being in all possible state

![[Pasted image 20231024155008.png]]

Used for getting the optimal state value function and policy.

# Deep Reinforcement Learning

1. Combined Deep Learning with Reinforcement Learning
2. Agent takes input as unstructured data
3. Agent learns to make decisions by trial and error
4. MDPs are high dimensional and RL algorithms uses Deep Learning to solve MDP
# Dynamic Programming

1. Problem Substructure - combining optimal solutions to smaller problems can be used to get the optimal value for the bigger problem
2. Not used for full Reinforcement Learning as full knowledge of MDP is required
# Experience

Experience (data for training RL) is continuous loop of observing a state, taking an action, getting a reward, then observing another state

# Markov Chain

1. States (assumes Markovian Property) connected to each other
2. State Transition Matrix

# Markov Reward Process

1. Markov Chain + Reward function showing immediate scalar returned for being in a state + Discounting Factor

# Markovian Property

1. state1 = f(history from x...y...z) 
2. state2= f(history from y...z), 

even if we drop history in state2 by ignoring data from x..y, we are not losing any information to determine what happens next

Probability of next state only depends on the previous state. Even if you take all the history, probability of next state will remain the same

# MDP

1. Markov Decision Process
2. Follows Markov Reward Process + ability to take actions
3. MDP can be discrete, continuous or Bandit, while action can be discrete or continuous
5. if we keep on sampling from State Transition Matrix and follow one after the another from this matrix, we get draws for the MDP
6. MDP is defined by (State,State Transition Matrix)

# Model

Predict how the environment will respond to an action
1. Transitions: predict what will be the next state given by the environment
2. Rewards: predict what will be the next reward given by the environment

# Policy

Mapping from state to action

1. Can be deterministic
2. Can be stochastic
	1. Useful for random exploratory behaviour
	2. Distribution of actions given a state
3. Does not depend on time because of Markov property that state holds all information for the future

# Policy Evaluation

Given a policy, calculate the total reward that can be collected in the MDP, i.e. state value function for all states
1. Start with 0 as state value function for all states
2. Iteratively apply Bellman Expectation Equation for MRP till convergence

# Policy Iteration

1. Uses Policy Evaluation as inner loop to improve the policy
2. Greedily go to neighbouring state with highest state value function, this becomes the policy
3. Now run policy evaluation again and greedy till convergence

# POMDP
1. We need to build the agent state instead of directly using the environment state as we did in MDP
2. As we don't know the environment state, we are create a probability distribution vector denoting where the agent may be in the environment state. This can be used to decide which action to take next
3. instead of dealing with probability vector, we can use a RNN that takes input as current observation and previous state to output the next state

# Reinforcement Learning

Agent sees an observation, takes an action and receives a Reward 
1. Goal is maximisation of expected rewards collected in an episode (Reward Hypothesis)
2. Agent(learns a Policy through algorithm trained on Experience) uses State to decide the next action 
3. If agent can fully observe all the states in the environment, then we can use environment state as agent state. This type of RL is formulated as MDP
4. If agent can observe the environment partially, then agent state is different from environment state. This type of RL is formulated as POMDP

# Return

Return for an "episode" is total cumulative Reward after applying discounting

Because of discounting, we have a geometric progression which gives a single value for value in the far future (horizon)

# Reward

Reward is the feedback signal. 
1. It is a single scalar number
2. It can be sparse/delayed

# State

State is a collection of history of observations

# State Transition Matrix

Possibility of subsequent states happening defined by probability distribution
	1. all transitions stored in this matrix

# Value Function

1. Prediction of future expected Return
2. State Value Function - based on a policy starting from State s in an "episode"
3. State Action Value Function - based on a policy starting from State s and taking action "a" in an "episode"
4. Bellman Expectation Equation for MRP

# Value Iteration

one forward optimal step assuming the subsequent state also follows the optimal policy

---
# References

1. https://www.youtube.com/watch?v=Nd1-UUMVfz4
2. https://www.youtube.com/watch?v=2pWv7GOvuf0
3. https://sassafras13.github.io/Silver2/
4. https://en.wikipedia.org/wiki/NP_(complexity)
