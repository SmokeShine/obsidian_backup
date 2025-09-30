202404021548
Status: #idea
Tags: [[Natural Policy Gradient]]

# Trust Region Policy Optimization (TRPO)

1. importance sampling to ensure there is more expected reward after update (first part of equation)
![[Pasted image 20250312144015.png]]
2. does not violate the constraint that KL divergence difference should be under a limit
![[Pasted image 20250312144100.png]]

All these methods are very similar to adam, rmsprop. Hack to speed up with little guarantee. Because the time commitment is so big, these hacks are necessary to get something feasible.

Trust region is KL divergence cap

---
# References

3. https://freedium.cfd/https://towardsdatascience.com/proximal-policy-optimization-ppo-explained-abed1952457b