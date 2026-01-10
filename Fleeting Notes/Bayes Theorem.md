202601021840
Status: #idea
Tags:

# Bayes Theorem

$${P\left(y/x)=\mathbb{P}\left(y\right.\cap x\right)}/{P\left(x\right)}$$

$${P\left(x/y)=\mathbb{P}\left(y\right.\cap x\right)}/{P\left(y\right)}$$

P(x/y) = P(y/x) * P(x) / P(y)

P(a,b/c) = P(a,b,c) / P(c)

P(a/b,c) = P(a,b,c)/P(b,c)

=> P(a,b/c) = P(a/b,c) * P(b,c)  / P(c)

=>  P(a,b/c) = P(a/b,c)  * P(b,c)  / P(c)

=>  P(a,b/c) = P(a/b,c)  * P(b/c)

Put $\theta$

=>  P(a,b/c, theta) = P(a/b,c, theta)  * P(b/c, theta)

Now, if we assume, 

p(f∣x,θ)=p(f∣θ)

p(f,y∣x,θ)=p(y∣f,x,θ)p(f∣θ)

=> $$P(f\vert y,x,\theta)=\frac{p(y\vert f,x,\theta)p(f\vert\theta)}{p(y\vert x,\theta)}$$

Now, P(y|x,theta can come from infinite functions. We will have to sum over all of them. This makes it intractable and we will to have [[Monte Carlo Learning]] or [[Sampling]]


Now, [[Posterior]] = [[Likelihood]] * [[Prior]] is incorrect.
It is proportional because of the denominator. First one is density, not probability.

---
# References

1. 