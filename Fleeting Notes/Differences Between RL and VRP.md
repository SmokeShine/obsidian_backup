202311161222
Status: #idea
Tags:

# Differences Between RL and VRP

1. RL assumption of MDP
	1. defining state that has markov property
	2. critic that gives good V(s)
	3. not sure how to respect constraints
	4. immediate reward - sparse reward cant recall, may be MC tree search by win/loss ratio
	5. competitive games - hand crafted features + tree search
	6. no generalisation - rules are fixed  in a game so hand crafted feature works
		1. RL generalisation is intractable at worst 
	7. VRP is a set while games have a sense of direction when creating feature vector
	8. VRP requires masking
	9. features can be seen as configuration - same as column generation
	10. a lot of explore-exploit strategies in RL
	11. value function needs to present all nuances of the game.
---
# References

1. https://arxiv.org/abs/2101.00300