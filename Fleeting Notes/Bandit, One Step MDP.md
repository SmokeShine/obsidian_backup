202310241040
Status: #idea
Tags: [[MDP]]

# Bandit

1. MDP with one state
2. Choose one state and episode ends

$$
\begin{gathered}
Reward=
\sum_{s} \text{probability of being in a state under stationary distribution} \\ \times \sum_{a} \text{probability of taking an action from a state under a policy} \\ \times \text{reward for taking that action} 
\end{gathered}
$$  
$$
\nabla J(\theta)=E_{\pi_\theta}[\nabla_\theta \log \pi_\theta(s,a) r]
$$

---
# References

1. https://www.youtube.com/watch?v=lfHX2hHRMVQ
2. https://www.youtube.com/watch?v=KHZVXao4qXs