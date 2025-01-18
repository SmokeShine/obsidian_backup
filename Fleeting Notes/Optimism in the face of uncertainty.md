202311091415
Status: #idea
Tags: [[Multi Armed Bandits]]

# Optimism in the face of uncertainty

dont pick the action with the highest return, but rather pick the action which has the possibility of giving the highest return in the future 

pick the one with highest upper confidence (95% tail of distribution)

for a very large space, we may keep on exploring and never exploit

for MDP, we can add a bonus on selecting a new action. As policy is always improving, this won't work well. RMax algorithm.

---
# References

1. https://www.youtube.com/watch?v=sGuiWX07sKw