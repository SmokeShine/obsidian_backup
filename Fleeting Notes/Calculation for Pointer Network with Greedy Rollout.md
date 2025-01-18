202409031432
Status: #idea
Tags:

# Calculation for Pointer Network with Greedy Rollout

# REINFORCE with Greedy Rollout Baseline for Seq2Seq Pointer Network in TSP

[[REINFORCE]] will try to maximize reward. But we have TSP. So, reinforce will try maximize -cost. As we are using gradient descent, which can only minimize, it will +cost again and then we can apply backward. A baseline is introduced to reduce variance. It should be subtracted.


---
# References

1. 