202408281423
Status: #paper
Tags:

# Solve routing problems with a residual edge-graph attention neural network

# Motivation
1. Use [[Graph Neural Network (GNN)]] that has capability for information embedding and message passing to provide polynomial time approximation for TSP/CVRP by training it end to end with [[Proximal Policy Optimization (PPO)]]

------

# Research question and objective
1. Effectiveness of Residual e-GAT for TSP and CVRP
2. Performance comparison with SOTA
	1. Concorde / LKH3 for TSP
	2. LKH-3 for CVRP
3. Impact of Hyperparameters - learning rate, batch size, number of iterations
4. Impact of Decoding Strategy with solution quality and compute time
5. Scalability
6. Training data efficiency compared to Kool et. al [[Attention, Learn to Solve Routing Problems]]

--------
# Strengths
1. End to End using GNN
	1. SDVRP - allows multiple touchpoints to meet a customer demand
2. TSP and CVRP till 100 nodes
	1. Benchmark TSPLib and CVRPLib
	2. Batch size 512, 128
		1. PPO epoch contains 800, 3000 batches
			1. 384k training samples
		2. Rollout epoch contains 1600, 6000 batches
			1. 768k training samples
	3. Trained for 100 epochs
	4. 10k test instances
3. New block called Residual E-GAT
	1. Updates [[Graph Attention Network (GAT)]] by adding edge information and residual connection between layers
	2. Uses [[Transformer]] for one step decoding instead of [[RNN]]
		1. Multi head attention with input used to create first [[Context Vector]]
		2. First context using simple attention with input to create probability pointers for [[Pointer Network]]
	3. Residual connection to avoid [[Vanishing Gradient]]
4. Uses [[Proximal Policy Optimization (PPO)]] 
	1. normalize reward like z-score = x -mean / standard deviation
	2. learning rate decay
	3. [[Xavier Initialisation]]
	4. Gradient clipping at 2
5. Uses [[Rollout Baseline]]
	1. Double actor critic
	2. Freeze the baseline and update the baseline after 10k evaluation
		1. perform [[paired t-test]] at 5%
6. Decoding 
	1. ~~[[Fleeting Notes/Beam Search|Beam Search]]~~
	2. ~~[[Neighbourhood search]]~~
	3. ~~[[Tree Search]]~~
	4. ~~[[Sampling]]~~
	5. ~~[[Active Search]]~~
	6. [[Greedy]]
		1. User at inference
	7. [[Stochastic Sampling]]
		1. Use temperature for diversity of samples
			1. Used at Training

# Weaknesses
1. No optimality guarantee
2. Homogenous vehicles
3. No limit on number of dispatch of trucks
---------

# Possible gaps and/or inconsistencies
1. 3 hop message passing in the code
	1. Can cause [[oversmoothing]] when using dense network for message passing
		1. No discussion
2. Compute at larger scale when using residual e-GAT
3. Generalization to other VRP types
	1. correlation among features between TSP and CVRP
4. No pickup, only delivery

--------

# Future work
1. Larger size
2. Masking is too simple and will not work for Simultaneous pickup and delivery
	1. Explore using heuristc and backtracking

------
# Short discussion
1. 

-----

# Relevance to your work
1. VRP using RL but it is not heterogenous and does not have simultaneous pickup and delivery
	1. The training part using PPO and rollout baseline can be beneficial
2. Benchmarking is very exhaustive - uses 3 DL models, 4 heuristics and 4 solvers
	1. Objective
	2. Optimality Gap
	3. Time
	4. Number of customers - 20/50/100
3. Other ways to create [[Graph Embedding]]
	1. Can [[Graph Tokens]] be used? how will they work for dense graphs

-------
# References

1. https://arxiv.org/abs/2105.02730

![[Pasted image 20240905160307.png]]
![[Pasted image 20240905160316.png]]
![[Pasted image 20240905160326.png]]
