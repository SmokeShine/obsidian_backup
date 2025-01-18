202409041122
Status: #paper
Tags:

# Deep Reinforcement Learning for Solving the Heterogeneous Capacitated Vehicle Routing Problem

# Motivation
1. Solve heterogenous which is often overlooked

------

# Research question and objective
1. solve the Heterogeneous by selecting both vehicles and nodes, considering different vehicle capacities.
2. Optimize for both min-max and min-sum objectives to minimize the longest or total travel time.

--------
# Strengths
1. heterogeneous fleet with different capacity
2. Ability to generalize to larger scale
3. Tries to apply masking for vehicle selection by max pooling and attention-softmax instead of direct masking
	1. Even if the vehicle is selection, the routes are later masked
4. Use same logic as [[Heterogeneous Attentions for Solving Pickup and Delivery Problem via Deep Reinforcement Learning]]
	1. Concat some part to create a big vector and then use attention
		1. Causes issues as customer vector has fixed length decided by number of vehicles
		2. But fixed lengths helps in running batches without padding


# Weaknesses
1. Complex model, can be slow
	1. Need a lot of compute
2. Number of vehicles are fixed
	1. Architecture is fixed for number of vehicles
3. If customer are coming from a different distribution (non uniform), performance is inferior
	1. out of scope generalization
---------

# Possible gaps and/or inconsistencies
1. Scalability
2. Does not check generalization for different number of vehicles
3. Does not provide example of vehicle selection by attention, but no more nodes that can be selected

--------

# Future work
1. 

------
# Short discussion
1. 

-----

# Relevance to your work
1. We can use this backbone and improve the architecture

-------
# References


![[Pasted image 20240905160040.png]]
![[Pasted image 20240905160049.png]]
![[Pasted image 20240905160058.png]]

