202512010942
Status: #idea
Tags: [[Linear Algebra]]

# Eigen Value

- If we apply a function on a vector, and it gets scaled
	- this function is linear transformation
	- for non linear, we first approximate it to linear transformation
- We do linear transformation with a matrix but it is just an approximation on original vector
	- the vector stops moving a lot after many iterations
	$Ax=\lambda x$
	=> (A - $\lambda I$)x = 0
		=> this means there is more than 1 solution, or more variables than equations, or determinant = 0
		=> this also ties up with approximation on original vector 
	Take determinant on LHS and find lambda
- with eigen, we can get a diagonal matrix which makes taking power easier
- ![[Pasted image 20251222230024.png]]
- for the case of weather prediction, where we need to apply transition matrix for n number of days, we can think of applying limit-> $\inf$, which will remove fractional probability of any weather type which has power to 0
	- because it is power, we can use eigen decomposition and apply power on the diagonal matrix
		- the first eigen value will dominate
			- matrix has largest value to smallest value
			- we know the number of eigen values from power of determinant
---
# References

1. https://learning.edx.org/course/course-v1:UTAustinX+UT.5.05x+1T2022/block-v1:UTAustinX+UT.5.05x+1T2022+type@sequential+block@31ad8e97d34c464c9ba58f2fc42272e9/block-v1:UTAustinX+UT.5.05x+1T2022+type@vertical+block@05a27255b9684cb5bf6932e69e15cedc
2. https://learning.edx.org/course/course-v1:UTAustinX+UT.5.05x+1T2022/block-v1:UTAustinX+UT.5.05x+1T2022+type@sequential+block@bdec56568f914fc495ef9f493e87094b/block-v1:UTAustinX+UT.5.05x+1T2022+type@vertical+block@77aab1939b2d42a9be84dfb3e2530bc9