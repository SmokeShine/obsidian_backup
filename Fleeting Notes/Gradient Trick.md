202311011300
Status: #idea
Tags: [[Policy Gradients]]

# Gradient Trick

![[Pasted image 20231101130033.png]]



**Policy**: Suppose the action aaa is binary (either 0 or 1), and the probability of choosing action 1 is given by:

p(a=1∣θ)=σ(θ)=11+e−θp(a=1|\theta) = \sigma(\theta) = \frac{1}{1 + e^{-\theta}}p(a=1∣θ)=σ(θ)=1+e−θ1​

where σ(θ)\sigma(\theta)σ(θ) is the **sigmoid** function, and θ\thetaθ is the parameter we are optimizing.

The probability of choosing action 0 is:

p(a=0∣θ)=1−σ(θ)p(a=0|\theta) = 1 - \sigma(\theta)p(a=0∣θ)=1−σ(θ)

1. **Log-likelihood for action 1**:
    
    log⁡p(a=1∣θ)=log⁡σ(θ)\log p(a=1|\theta) = \log \sigma(\theta)logp(a=1∣θ)=logσ(θ)
    
    And the gradient of the log-likelihood for action 1 with respect to θ\thetaθ is:
    
    ∇θlog⁡p(a=1∣θ)=1−σ(θ)\nabla_{\theta} \log p(a=1|\theta) = 1 - \sigma(\theta)∇θ​logp(a=1∣θ)=1−σ(θ)
2. **Log-likelihood for action 0**:
    
    log⁡p(a=0∣θ)=log⁡(1−σ(θ))\log p(a=0|\theta) = \log (1 - \sigma(\theta))logp(a=0∣θ)=log(1−σ(θ))
    
    And the gradient of the log-likelihood for action 0 with respect to θ\thetaθ is:
    
    ∇θlog⁡p(a=0∣θ)=−σ(θ)\nabla_{\theta} \log p(a=0|\theta) = -\sigma(\theta)∇θ​logp(a=0∣θ)=−σ(θ)

Now, using the **log-likelihood trick**, the gradient of J(θ)J(\theta)J(θ) can be written as:

∇θJ(θ)=Ea∼p(a∣θ)[r(a)∇θlog⁡p(a∣θ)]\nabla_{\theta} J(\theta) = \mathbb{E}_{a \sim p(a|\theta)} [r(a) \nabla_{\theta} \log p(a|\theta)]∇θ​J(θ)=Ea∼p(a∣θ)​[r(a)∇θ​logp(a∣θ)]

This becomes:

∇θJ(θ)=r(1)⋅p(a=1∣θ)⋅(1−σ(θ))+r(0)⋅p(a=0∣θ)⋅(−σ(θ))\nabla_{\theta} J(\theta) = r(1) \cdot p(a=1|\theta) \cdot (1 - \sigma(\theta)) + r(0) \cdot p(a=0|\theta) \cdot (-\sigma(\theta))∇θ​J(θ)=r(1)⋅p(a=1∣θ)⋅(1−σ(θ))+r(0)⋅p(a=0∣θ)⋅(−σ(θ))

Substituting the reward values r(1)=10r(1) = 10r(1)=10 and r(0)=5r(0) = 5r(0)=5 and simplifying, you get:

∇θJ(θ)=10⋅σ(θ)⋅(1−σ(θ))−5⋅(1−σ(θ))⋅σ(θ)\nabla_{\theta} J(\theta) = 10 \cdot \sigma(\theta) \cdot (1 - \sigma(\theta)) - 5 \cdot (1 - \sigma(\theta)) \cdot \sigma(\theta)∇θ​J(θ)=10⋅σ(θ)⋅(1−σ(θ))−5⋅(1−σ(θ))⋅σ(θ)

This simplifies to:

∇θJ(θ)=(10−5)⋅σ(θ)⋅(1−σ(θ))\nabla_{\theta} J(\theta) = (10 - 5) \cdot \sigma(\theta) \cdot (1 - \sigma(\theta))∇θ​J(θ)=(10−5)⋅σ(θ)⋅(1−σ(θ))

So, the gradient of the expected reward is:

∇θJ(θ)=5⋅σ(θ)⋅(1−σ(θ))\nabla_{\theta} J(\theta) = 5 \cdot \sigma(\theta) \cdot (1 - \sigma(\theta))∇θ​J(θ)=5⋅σ(θ)⋅(1−σ(θ))

---
# References

1. https://www.youtube.com/watch?v=KHZVXao4qXs