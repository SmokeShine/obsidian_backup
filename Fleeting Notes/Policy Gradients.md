202310311221
Status: #idea
Tags: [[Policy]]

# Policy Gradient

Optimize policy directly instead of dealing with V(s) by looking at samples. Adjust policy in the direction which makes the policy better

Instead of V(s,theta), we try P(a/s,theta) -  Policy in general is the action to take for a given state. Now, for a given theta, which policy to use. Or from a given policy, use theta to decide the action. 

1. No need to worry about max Q(s,a)
2. Less memory as no Q(s,a)
3. No chatter
4. High variance and slow

Policy gradient calculation becomes $\inf$ as we policy improves. Issue with policy gradient methods

Tune $theta$ so that policy moves in a direction with better rewards. Parameters dictate which action will be probabilistically chosen.

---
# References

1. https://www.youtube.com/watch?v=KHZVXao4qXs