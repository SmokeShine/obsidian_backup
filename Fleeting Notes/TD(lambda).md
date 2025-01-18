202310261531
Status: #idea
Tags: [[Model Free]]

# TD(lambda)

n steps of real rewards and after that, estimates of state value function 

introduce lambda and decay weights geometrically to steps of n sizes from start, and then sum them up to use it as target


so, as it is decaying, later steps would have negligible contribution. 

Forward view of TD(lambda) is episodic
Backward view can work 

1. In forward view, we have rewards and returns from the future. 
2. In backward view, we use a derived variable called eligibility trace which provides traces from the past, this can now be used to update v(s) based on difference between the expected value and approximation

---
# References

1. https://www.youtube.com/watch?v=PnHCvfgC_ZA