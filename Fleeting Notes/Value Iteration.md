202310251511
Status: #idea
Tags: [[MDP]]

# Value Iteration

1. Instead of solving all states in policy evaluation inside policy iteration, if we take only one iteration for one state in policy evaluation, it becomes value iteration
2. one forward optimal step assuming the subsequent state also follows the optimal policy
3. Uses [[Bellman Optimality Equation]] directly, and hence we are not creating any intermediate policy, and hence any intermediate state function may not correspond to a policy

---
# References

1. https://www.youtube.com/watch?v=Nd1-UUMVfz4