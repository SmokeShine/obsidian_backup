202512152034
Status: #idea
Tags: [[Linear Algebra]]

# Inverse of Matrix

- AB = I
	- So, we find a matrix which when multiplied will give identity matrix
- If A is a diagonal matrix, B would element wise division of diagonal. This is easy as there is only element in the column and we need to get 1. Rest will give zero
- [[Gaussian Elimination]] tries to get an upper diagonal matrix. So, by pivoting and subtracting rows, we can get a diagonal matrix and then divide similarly as previous step
- Inverse is tied to determinant not equal to zero
	- $A$ * ($1/Determinant$  * $A$) = Identity matrix
	- So, ($1/Determinant$  * $A$) =  $A^-1$
- It is a very expensive operation even when we know the algorithm
- During [[LU Factorization]], if the diagonal has a zero, we cannot divide by zero and the inverse will not exist
	- so, if two equations are same, subtracting will give 0 even on diagonal and hence zero determinant and matrix has no inverse
---
# References

1. https://learning.edx.org/course/course-v1:UTAustinX+UT.5.05x+1T2022/block-v1:UTAustinX+UT.5.05x+1T2022+type@sequential+block@65bfdc23a34d48a6902c8449e609c001/block-v1:UTAustinX+UT.5.05x+1T2022+type@vertical+block@50b0f6596c4d4b7d8108efa98c268794
2. https://learning.edx.org/course/course-v1:UTAustinX+UT.5.05x+1T2022/block-v1:UTAustinX+UT.5.05x+1T2022+type@sequential+block@65bfdc23a34d48a6902c8449e609c001/block-v1:UTAustinX+UT.5.05x+1T2022+type@vertical+block@d49890518cfb4fdd947ccfac3d8c5665