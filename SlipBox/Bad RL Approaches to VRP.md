202311071446
Status: #idea
Tags: [[Issues with RL]]

# Bad RL Approaches to VRP

1. Actor Critic - Critics needs to tell what would be the final solution on pickup an action. This cant generalize with changes in VRP sizes
2. Difficult to define state in VRP - binary variables value at each iteration? It becomes POMDP as information is lost and is not sufficient to predict the future
3. Exploration is seed dependent
4. Too many actions for one reward - credit assignment problem
5. Building a reliable critic is very hard - it can learn Q(s,a) for atari agent so there is enough capacity to learn but it is unable to learn
	1. So policy based RL that avoids creating a critic
		1. DIMACS
			1. But slow convergence
			2. Local optima
6. No parent to learn from - predict the variance of HGS result
	1. What is HGS???
---
# References

1. https://www.youtube.com/watch?v=nGc1MVNRvjE
2. https://openreview.net/forum?id=C__ChZs8WjU