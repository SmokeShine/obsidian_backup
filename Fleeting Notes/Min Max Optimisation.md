202311161119
Status: #idea
Tags:

# Min Max Optimisation

Strategy for playing games

1. Nash Equilibrium - one strategy that dominates all other strategies 
	1. treat other play as part of environment
	2. finding counter strategies and if a fixed point is reached, then it is nash equilibrium
	3. joint policy for set of players
2. Perfect information and imperfect information
3. alpha beta search - remove parts which may not be visited (same as fathom?)

In checkers, because of dice, there is randomness (from one state to another, we are not confident how much the value will increase) and hence the V(s) is smooth and neural network can be used.

- for HCVRP, min max optimisation would be minimizing the longest route for the vehicle instead of minimizing the total sum of all the routes
	- for fairness, instead of total sum, min max is better to avoid one vehicle to be abused to cover everything
---
# References

1. https://www.youtube.com/watch?v=kZ_AUmFcZtk
2. https://arxiv.org/abs/2110.02629