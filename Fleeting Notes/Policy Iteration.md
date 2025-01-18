202310251300
Status: #idea
Tags: [[Bellman Equation for MRP]]

# Policy Iteration

1. Uses [[Policy Evaluation]] as inner loop to improve the policy
2. Greedily go to neighbouring state with highest state value function, this becomes the policy
	1. This is same as max(q-value) for that state-action value function.
3. Now run policy evaluation again and greedy till convergence
4. Even though we started with [[Bellman Equation for MRP]], at stoppage, it will satisfy the criteria for [[Bellman Optimality Equation]] 


---
# References

1. https://www.youtube.com/watch?v=Nd1-UUMVfz4