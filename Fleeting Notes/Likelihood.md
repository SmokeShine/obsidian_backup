202512311239
Status: #idea
Tags: [[Probabilistic Machine Learning]]

# Likelihood

y = wx + noise.

We assume noise is Gaussian. We assumed weights are Gaussian. So, we can write y in vector form. When we see a point, we need to adjust the mean as they are sum of two Gaussian. But, covariance of weights will change.  When we do the adjustment after seeing a data, it is called likelihood. P(y|w,noise)

[[Posterior]] is change in distribution of [[Prior]] weights based on likelihood update of each data point

---
# References

1. 