202409041125
Status: #paper
Tags:

# Pointer Networks

# Motivation
1. DL network to handle variable size output dictionary not known in advance and points to input token

------

# Research question and objective
1. Design architecture that can solve [[Combinatorial Optimisation Problems]]
	1. Finding convex planar hulls
	2. Delaunay Triangulation
	3. [[TSP]]
2. Generalize beyond training for tokens not seen during training

--------
# Strengths
1. Handle variable length output which [[Seq2Seq]] can't handle if output dictionary size is not known beforehand
2. Does not use context vector
	1. Passes hidden state from encoder to decoder
3. Good approximate solutions
4. can work for unseen token during trainings

# Weaknesses
1. RNN is sequentially rolling
	1. slow and cannot be parallelized
	2. input nodes are set, and hence we need to provide all permutations for training
2. Supervised learning
	1. May not work on increasing scale
	2. depends on heuristics performance quality on selected problem
---------

# Possible gaps and/or inconsistencies
1. Context vector was not used but following papers in attention/residual, reintroduce context embedding because they want to use transformer attention
	1. Context vector is single point of compression

--------

# Future work
1. Use RL

------
# Short discussion
1. Context vector was skipped as it would lead to too much compression when used with large sequence
	1. Directly pass encoder hidden state to decoder
	2. Following paper use context vector along with attention but enhance them by using mean embeddings
		1. so some information is retained
		2. no need to save all embeddings
			1. Graph embedding is mean, if it is weighted it becomes [[Residual Edge-Graph Attention Network (residual E-GAT)]]

-----

# Relevance to your work
1. 

-------
# References

1. https://arxiv.org/abs/1506.03134
2. https://github.com/shirgur/pointernet

![[Pasted image 20240905160139.png]]
