202401311342
Status: #idea
Tags: [[Pointer Network]]

# Reinforcement Learning for Solving VRP

# Data Creation
1. Depot with random values on 1st index
2. Create random points for fixed batch size from 1x1 square
3. Demand 
# Model
## Encoder
1. CNN filter on (x,y) to increase the dimensionality from 2 to 256/512
2. CNN filter on demand to increase the dimensionality from 2 to 256/512
	1. (demand,vehicle capacity - demand)
3. output from both layers of demand and (x,y) without concatenation/summation
## Decoder
1. depot embedding as input start token
2. LSTM cell running over time steps
3. hidden state of the decoder initialised with 0s
4. Decode one state
	1. Attention
		1. mask 
			1. cities no demand left
			2. cities demand > capacity left
			3. all cities if no capacity left on truck
			4. depot is never masked
				1. depot is always chosen if all cities are visited
		2. output from decoder with attention from encoder outputs
			1. concatenate both static and dynamic embeddings 
				1. if a customer is visited, output will be masked by the masking scheme
		3. find index for the max value
		4. Reduce truck load
		5. Reduce customer demand
			1. used for masking scheme
	2. Max index
	3. embedding of the (x,y) coordinate of the index used as input for next time step
5. Stop decoding till n number of iterations

# Training
1. Actor
	1. Encoder-decoder is the actor
	2. log probabilities, max index is used
		1. using max index, calculate the total reward using distance matrix
2. Critic
	1. used only static embeddings, not dynamic
	2. output a scalar for n iterations
3. [[Advantage function]]
	1. reward is 0 at start
	2. reward at each time step - critic output for each time step
		1. reward is 0 for staying at depot
		2. possible issue where model learns to stay at depot and not move for all iterations
			1. penalty for staying idle
			2. vehicle will always stay at depot because of 0 distance
				1. it is useful to stay on depot when all cities are visited
				2. can't force movement as in heterogenous case, some vehicles staying at depot may be preferred way
					1. shared masking scheme

---
# References

1. https://arxiv.org/abs/1802.04240
2. https://github.com/SmokeShine/Reinforcement-Learning-for-Solving-the-Vehicle-Routing-Problem