202501141530
Status: #idea
Tags: [[Variational Autoencoder]]

# Prior

1. It may be difficult to sample from data distribution which is unknown
2. Instead we can sample from simple distribution like gaussian, this is called prior
3. The task is to make sure the prior is very close to data distribution and this acts as a proxy and we can sample
4. p$_\theta$(z)

Prior is assumption of distribution of x => P(x) => If dependent variables are gaussian, adding, scaling and multiplying will also be Gaussian and we can calculate them by formulae
[[Posterior]] is P(x/dependent variables) => I can get this from data. If it is assumed gaussian, it will have a mean and variance from the data.
[[Likelihood]] is P(dependent variables/x). If i know the mean of x and i see a different mean, I need to calculate what is the probability of that happening as that data is still possible from the distribution

Posterior = Prior * Likelihood
= if we multiply this two gaussian distribution, we get another gaussian distribution but it is not [[Probability Density Function]]. It won't sum to 1. 

---
# References

1. https://www.youtube.com/watch?v=yQvELPjmyn0