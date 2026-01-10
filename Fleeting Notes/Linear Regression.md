202512221136
Status: #idea
Tags: [[Column Space]]

# Linear Regression

- this is similar to how we find the distance of point from a line. 
	- we need to find the point on line from which we can draw perpendicular to the point
		- this point is minimize the distance in itself
		- altitude will provide the least distance
		- then this altitude itself is a vector from point A to B
	- So, column space of A can find the point from which we can draw the altitude
		- if we do this for all possible raw data points, this itself becomes a subspace
		- but we know from dot product that perpendicular will give 0
			- $e = b - A\hat{x}$
				- if i sum up everything, this is [[Root Mean Squared (RMSE)]]
			- $A^T(b - A\hat{x}) = 0$
		- so, we do a dot product = 0  for A.T* perpendicular vector
			- .T comes from definition of dot product, that does not mean A.T is orthogonal
			- this perpendicular vector is [[Orthogonal Projection]]

	[[Probabilistic Machine Learning]]

Assume prior is Gaussian with zero mean and identity covariance matrix.  But how many features do we have? if we have only one feature, and because of bias, we will have two features.  Both the weights are unknown. We have assume Gaussian distribution. So, this becomes the [[Prior]] for the weights. We have one prior and not two. They have a mean and a covariance matrix P(w).  
[[Posterior]] will be P(w|y,x) which P(w) * P(y|w,x). But because all three are Gaussian, we cannot sample but need to solve with matrices. Because of [[Iterative Solvers]] way of looking at data points, we have formula for posterior mean and posterior covariance. As we see more data, this covariance will reduce. So, even though we thought weights were unknown, in [[Probabilistic Machine Learning]], it only means they have uncertainty, as we know they lie somewhere between 0 and 1 covariance.

If posterior is not Gaussian, as in case of [[Deep Learning]], we will have to use [[Sampling]] such as [[Monte Carlo Learning]]

Then take derivative on log. This can be put into any optimizer such as [[SGD]]. We will get two components. Prior now works as [[Regularization]].

As we know the function is linear combination of x.  We can get Gaussian for the function themselves P(function|y,x). We do this instead of getting a single y, because we want confidence interval.

---
# References

1. https://learning.edx.org/course/course-v1:UTAustinX+UT.5.05x+1T2022/block-v1:UTAustinX+UT.5.05x+1T2022+type@sequential+block@89219ffd97b8461fb01f0959f7ff82ea/block-v1:UTAustinX+UT.5.05x+1T2022+type@vertical+block@05857a154bf4413fb66bb29cba825220
2. https://www.youtube.com/watch?v=R92IGe-OrzM&list=PL05umP7R6ij0hPfU7Yuz8J9WXjlb3MFjm&index=5
3. https://www.youtube.com/watch?v=1Cj5tSYE8IQ&list=PL05umP7R6ij0hPfU7Yuz8J9WXjlb3MFjm&index=7