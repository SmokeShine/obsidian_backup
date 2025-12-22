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
			- $$A^T(b - A\hat{x}) = 0$$
		- so, we do a dot product = 0  for A.T* perpendicular vector
			- .T comes from definition of dot product, that does not mean A.T is orthogonal
			- this perpendicular vector is [[Orthogonal Projection]]
		
---
# References

1. https://learning.edx.org/course/course-v1:UTAustinX+UT.5.05x+1T2022/block-v1:UTAustinX+UT.5.05x+1T2022+type@sequential+block@89219ffd97b8461fb01f0959f7ff82ea/block-v1:UTAustinX+UT.5.05x+1T2022+type@vertical+block@05857a154bf4413fb66bb29cba825220