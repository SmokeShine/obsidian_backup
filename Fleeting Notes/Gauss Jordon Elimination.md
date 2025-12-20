202512171139
Status: #idea
Tags: [[Gaussian Elimination]]

# Gauss Jordon Elimination

- Same but with rows swapping and changing pivot and multiplying before subtracting
- instead of upper diagonal matrix, we try to make it identify matrix, then we get the solution by reading the elements of the diagonal instead of putting one value and applying upwards previously
- Ax = b
	- We use matrix * vector, match values and get values for x
- F($A$x) = x
	- Inverse would mean we apply a function and another function on top of it, and we get original vector
		- so, that F is another linear transformation given by matrix and called inverse
		- So, $A^-1 * Ax$=$x$
		- but we know $I*x=x$; so $A^-1 * A=I$
	- Same as before but now we know b is identify matrix
		- solve like before
- With Gauss Jordon, we can have two values for b
	- Ax1 = b1
	- Ax2 = b2
	- So, we solve them with 
		- |A,x1,x2 = |b1,b2|
			- they are stack horizontally
	- so, this can help in making Ax = b => Ix = b*$A^-1$
	- Now, we have two methods to get inverse of a matrix
		- Gaussian elimination still requires solving equation once we get the last value and substituting them in rest of the equations
		- Gauss Jordon can do that without solving and back substituting
- Cost of inverting is $2n^3$
---
# References

1. https://learning.edx.org/course/course-v1:UTAustinX+UT.5.05x+1T2022/block-v1:UTAustinX+UT.5.05x+1T2022+type@sequential+block@dee2cc3144584d25950c8a756fd47533/block-v1:UTAustinX+UT.5.05x+1T2022+type@vertical+block@d6a72389ca1248aa9d6f98a7e259f820
2. https://www.youtube.com/watch?v=qKhNd8wUDGU