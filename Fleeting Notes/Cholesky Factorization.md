202512171543
Status: #idea
Tags: [[Linear Algebra]]

# Cholesky Factorization

$A=L.L^T$
Similar to [[LU Factorization]], this is another factorization method into two 	
- Cholesky is a variant of LU factorization
	- both are lower triangular matrix and not Lower + upper
		- because upper triangular can be seen as transpose of lower triangular matrix
	- But A has a special initial requirement
		- L is lower triangular matrix 
- A is symmetric positive definite
	- Symmetric -  A = A.T
	- All [[Eigen Value]] are positive
	- All pivots are positive
	- All subdeterminants are positive
	- Could be like correlation or distance matrix so that it is symmetric
- They have two formulae
	- one for diagonal
	- another for non diagonal

---
# References

1. https://learning.edx.org/course/course-v1:UTAustinX+UT.5.05x+1T2022/block-v1:UTAustinX+UT.5.05x+1T2022+type@sequential+block@e4b0c93da78c44d3854fa56b364d0189/block-v1:UTAustinX+UT.5.05x+1T2022+type@vertical+block@faabb2c3387e47c4b95cb1435ec9c405
2. https://www.youtube.com/watch?v=CBkdQSu7NnY