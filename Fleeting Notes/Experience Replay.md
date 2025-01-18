202310301605
Status: #idea
Tags: [[Value Function Approximations]]

# Experience Replay

1. Given tuple of (state, value function from oracle), create  a function that minimizes least square
2. As the value function is from oracle, we can sample the past (state, value function) from experience replay and apply SGD
3. As we are sampling, we are breaking non iid, and making it iid.
---
# References

1. https://www.youtube.com/watch?v=UoPei5o4fps