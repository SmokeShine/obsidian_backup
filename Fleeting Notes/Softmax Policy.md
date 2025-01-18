202310311612
Status: #idea
Tags: [[Monte Carlo Policy Gradient]]

# Softmax Policy

$$\phi(s,a) $$ are features. Can treat as x in theta transpose.X

1. Softmax 
	$$\pi(s,a) = \frac {e ^ {\phi(s,a) ^\intercal \theta} } { \sum_{k=1}^N e ^ {\phi(s,a) ^\intercal \theta}}$$
3. score is $$\nabla \log \pi(s,a) = \phi(s,a) - E[\phi(s,.)$$
4. this derivative is what [[REINFORCE]] is looking for when computing gradients for maximizing reward

---
# References

1. https://www.youtube.com/watch?v=KHZVXao4qXs
2. https://math.stackexchange.com/questions/2013050/log-of-softmax-function-derivative