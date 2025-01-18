202408291530
Status: #paper
Tags:

# Attention, Learn to Solve Routing Problems!

# Motivation
1. Train a DL model with same set of hyperparameters that can solve different problems for a variant of VRP
2. Heuristics can be seen a DL model with parameters where rules to make decisions are embedded in the weights

------

# Research question and objective
1. Unified attention model to solve four variants of routing problem
	1. [[TSP]]
	2. [[VRP]]
	3. Prize Collecting TSP
	4. Orienteering Problem
2. Performance comparison with SOTA
	1. Concorde / LKH3/ Gurobi for TSP
	2. LKH-3/Gurobi for CVRP
	3. Gurobi/Compass for [[Orienteering Problem]]
	4. Iterated local search/ Gurobi for [[Prize Collecting TSP]]
3. Impact of hyperparameters -learning rate, batch size, number of iterations
4. Impact of Decoding Strategy with solution quality and compute time
5. Training data efficiency

--------
# Strengths
1. End to End GAT
	1. Encoder is attention
		1. Stack n-headed multi attention twice
			1. No parameter sharing between stacking
		2. node embedding and mean graph embedding input for decoder
		3. No positional encoding as [[Transformer]]
		4. use [[Skip Connection]] and [[Batch Normalization]] instead of [[Layer Normalization]]
	2. Decoder is attention
		1. Context uses first and previous node selected
			1. learnable weights at time 0
			2. Order and in between nodes does not matter for returning back to the first spot and complete the tour
	3. Mask before clipping and apply log to get [[logits]]
		1. apply [[Softmax Policy]] to get probability score
		2. when calculating gradient, log_p is summed for all the decoded nodes in the tour 
			1. p1 * p2 will become sum when applying log
2. Fast Decoding
	1. To avoid O(n^2) decoding, only interacts with context vector to make O(n)
		1. While encoding has all n, decoding will only look at context to get next node![[Pasted image 20240904115444.png]]
		2. So, key and value are coming from encoder node embeddings, while query is coming from context node  
	2. No skip connection, batch normalization, feed forward hidden layer for maximum efficiency of decoding
3. Very simple baseline using [[Rollout Baseline]] for speed instead of creating a network for critic in [[Actor Critic Policy Gradient]]
	1. Baseline will be greedy eval of an old policy to get the cost
	2. L(π) is sampled path from current policy, could be greedy or categorical sample
	3. If the difference is significant, then baseline is updated and new evaluation data is introduced
		1. copy the weights of current policy onto baseline policy and do exponential moving average as usual
4. Use larger batch size and baseline can be run in eval mode without gradients for the batch
5. No finetuning on other tasks, using same hyper parameters on all four tasks
6. Better than [[Pointer Network]]
	1. Dynamic context which can access input values directly with first and previous node selection, instead of [[RNN]] encoder output state which may have compressed information
	2. Multi headed attention can be parallelized 

# Weaknesses
1. No optimality guarantee
2. Homogenous vehicles
3. No limit on number of dispatch of trucks
4. Does not beat traditional methods
5. Depends on baseline and seed
	1. may be the reason TSP was not chosen and not harder tasks
---------

# Possible gaps and/or inconsistencies
1. Rollout baseline can lead to slow convergence as it is focussing on variance. If the critic can learn some patterns, then it will boost the convergence 
2. Does not tell how to create masks for other variants, because they can't be greedily selected or turned on/off easily
3. Why use same hyperparameters and fine tune for task and then check correlation between weights
	1. Why tuning was done only on TSP to find the common set of hyper parameters
		1. was the training not stable and impacted by random seed in other tasks?
		2. Gradient calculation in TSP is at each decoded node, while for VRP it is for complete tour
			1. the tour length may differ for VRP between baseline and policy

--------

# Future work
1. Scale training
2. Improved masking that uses heuristics and backtracking for complicated VRP variants
3. Generalize to larger instances

------
# Short discussion
1. It is an application and focuses on how to get good heuristic solutions fast with O(n) attention

-----

# Relevance to your work
1. Using same hyper parameters may be beneficial for cases where only pickup, only delivery, both pickup and delivery are involved
	1. No need to train three different models
2. Can be useful when human learnt heuristic is difficult to make 

-------
# References

1. https://github.com/wouterkool/attention-learn-to-route/tree/master
2. https://arxiv.org/abs/1803.08475

![[Pasted image 20240905155849.png]]

![[Pasted image 20240905155857.png]]
