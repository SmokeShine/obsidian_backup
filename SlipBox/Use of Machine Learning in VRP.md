202311201034
Status: #idea
Tags:

# Use of Machine Learning in VRP


Can learning interesting graph motifs on its own. 
	- when combined with layers, this will acts as combination of presence of different number of motifs
		- but that will be useful for classification; it means for solving a problem, we have collection of prepared motifs that may be useful for finding a route with similar constraints
			- how to define constraints in deep learning/machine learning?

1. If label data is present, it can be converted to supervised learning
	1. Use exact solution/heuristics to learn policy
		1. heuristics generally have better performance
2. Unsupervised does not work well
3. Reinforcement Learning can be used to create labels but is sample inefficient and does not generalize
	1. New explore-exploit method with guarantees
	2. Policy approximation - does not generalize to changes in environment
		1. Dimes
	3. Solve linear programming problems with deep learning by allowing changes on right hand side scalar on constraints; no change in objective function
	4. New neural architecture - draw something parallel from electrical engineering/SCM
		1. Discretization of continuous values - pull back to anchor if very far (went to forbidden zone)
	5. Graph neural network - encode neighbour information/ all network metrics like density to create a representation
		1. Need a way to say two graphs are same - isomorphic
	6. Iteratively improve heuristics such as 2-opt or decode MDP to get next state such as pointer network
---
# References

1. https://www-sciencedirect-com.proxy.bnl.lu/science/article/pii/S0925231222014412
2. https://www-sciencedirect-com.proxy.bnl.lu/science/article/pii/S0925231222014412