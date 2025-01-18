202501071538
Status: #paper
Tags: [[ICORES]]

# Integrating Machine Learning and Optimisation to Solve the Capacitated Vehicle Routing Problem

# Motivation
1. [[Graph Neural Network (GNN)]]/ [[Graph Attention Network (GAT)]] + [[REINFORCE]] is slow and computationally expensive, can we find cheaper alternatives
------

# Research question and objective
1. Performance of [[DiCE The Infinitely Differentiable Monte Carlo Estimator]] which provides unbiased gradient updates when solving [[Neural Combinatorial Optimization]] problems like [[TSP]] and [[CVRP]]
	1. [[Optimality Gap]]
	2. Variants
		1. GAT + REINFORCE
		2. DICE
		3. DICE + [[MISH]] Activation - [[Batch Normalization]] layers

# Architecture
1. Input
	1. Node - x,y,q
		1. x,y coordinate and demand for customer
		2. Depot demand is 0
	2. Edge - distance between two cities
	3. Passed to a [[Fully Connected Linear Layer]] 
		1. d$_x$
		2. d$_e$
	4. Batch Normalization
2. Data Ready for Encoder
3. GAT
	1. Update the vertex attributes through attention
	2. Edge attributes not changed, only concatenated during attention
4. [[Attention]] 
	1. Concatenate vertex attribute (i) and (j) and (edge between i and j)
		1. Passed through learnable matrix to give a vector
		2. Passed through learnable vector
		3. [[Leaky Relu]]
5. Stacking of Layers
	1. Update vertex attribute
		1. Previous layer attribute + (weighted sum of all attention $*$ Learnable weight matrix $*$ previous layer  attribute)
6. After stacking, take mean of all vertex attribute from the final layer to create a [[Context Vector]]
7. Data ready for decoder
8. [[Multi headed Attention]] + [[Pointer Network]]
	1. No Batch normalisation
	2. No Residual Connection
	3. No Fully Connected Layers
9. Previous Decoding + Encoder vector representation = Next vertex on route
10. Layer 1 Decoder produces a layer 2 context vector using multi head attention
	1. Encoder Context vector (mean) + Last selected vertex in route + First selected vertex in route
	2. 3 Learnable Weight Matrices - Key, Value and Query for each head
	3. If a vertex was previously selected, for next selection, attention is made $-\inf$, such that soft max converts this to 0
	4. Repeat this for H heads
	5. 1 More learnable weight matrix after concatenating all attention probability from H heads
		1. Note - attention probability is probability and hence we multiply it with values (= weight matrix of Value $*$ node attribute from encoder after residual weighted sum)
		2. Do for all the vertices
		3. Sum for each head
		4. Concatenate value from each head
		5. Pass through a learnable matrix to create context vector
	6. Context vector created
11. Layer 2 Decoder uses 1 Head attention to create attention score
	1. context vector $*$ key vector / dimensionality
	2. Apply [[Tanh]] activation function to restrict it to $[-1,1]$
	3. Multiple by C to restrict the value to $[-C,C]$
	4. This is attention score
12. Apply softmax to get probability and select the next route

## REINFORCE
1. Loss = Expected reward of the [[Policy]]
	1. As it is expectation, we use [[Gradient Trick]] and use [[REINFORCE]] to get gradients on improving policy
	2. To reduce variance, we use a baseline
2. Use frozen model and apply [[Greedy Rollout Baseline]] from [[Attention, Learn to Solve Routing Problems!]]
	1. Take greedy steps based on best probability from the frozen model - this is baseline
	2. Keep on updating the other model
	3. At the end of epoch, check against old actor copy on validation set
		1. replace old actor copy if new actor is better
	4. This process is similar to [[Deep Q-Network(DQN)]] replacement
## DiCE
1. Fixes higher older derivative calculation in autograd
	1. Correct calculation will stabilize variance
2. Uses [[Stochastic Computation Graphs]] for defining stochastic vertices
	1. Choice made by actor
	2. Objective function
		1. Distance travelled
3. As we have stable gradient updates, we can remove baseline as it was only included for stabilizing gradients
## DiCE Mish
1. For improving gradient flow during [[backpropogation]]
2. Replacement
	1. LeakyRelu with Mish
	2. Tanh with Mish
3. Removal of batch normalization

## Metrics (on test cases)
1. Average distance 
2. Average distance relative to untrained model
3. Average time to solution
4. Total time

## Hardware
1. GTX 1660 Super with 6 GB VRAM
2. 2.5 GHz Intel CPU
3. 32 GB RAM

# Test bed
1. 21 vertices for DL models comparison
2. 11 vertices for exact with GAT
3. 768k training instances with coordinates sampled from 1 $x$ 1 
4. 100 epochs
5. 512 batch size
6. SCIP Exact Solver
--------
# Strengths
1. Similar performance but DiCE does not need dual actor leading to reduction in computational overhead
	1. Need to optimize only one actor instead of two
	2. 20 hrs vs 14 hrs
2. Faster than exact methods
3. Time is expensive resource when solving VRP, this optimisation may be useful

# Weaknesses
1. Can we use higher learning rate if variance is stable with DiCE? 
2. Out of scale performance
	1. trained on 20 but tested on 30/40/50. How performance degrades
---------

# Possible gaps and/or inconsistencies
1. Ablation study is done but the word itself is not used
2. Example of route created
3. Usage with newton method
4. No Diagram of Stochastic computation graph

--------

# Future work
1. Other VRPs where masking is trivial
2. Warm start strategy may be different because we now have stable gradient updates
3. For improving out of scale performance, [[Neural Combinatorial Optimization with Heavy Decoder]]

------
# Short discussion
1. 

-----

# Relevance to your work
1. 

-------
# References

1. 