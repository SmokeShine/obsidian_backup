202404021548
Status: #idea
Tags: [[Natural Policy Gradient]]

# Trust Region Policy Optimization (TRPO)

1. importance sampling to ensure there is more expected reward after update
2. does not violate the constraint that KL divergence difference should be under a limit


All these methods are very similar to adam, rmsprop. Hack to speed up with little guarantee. Because the time commitment is so big, these hacks are necessary to get something feasible.

---
# References

1. https://freedium.cfd/https://towardsdatascience.com/proximal-policy-optimization-ppo-explained-abed1952457b