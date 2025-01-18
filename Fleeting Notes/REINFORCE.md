202311011321
Status: #idea
Tags: [[Monte Carlo Policy Gradient]]

# REINFORCE

1. Instead of expectation in Monte Carlo Policy Gradient, replace Q(s,a) with the return we received at that state for taking that action
	1. so we are estimating Q(s,a) using return
2. Update parameters by stochastic gradient ascent
3. Extremely slow as it uses complete episodes

So, if policy is a linear combination of features and is differentiable, we can use Reinforce to improve the weights of the policy

---
# References

1. https://www.youtube.com/watch?v=KHZVXao4qX