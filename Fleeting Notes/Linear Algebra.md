202512072042
Status: #idea
Tags:

# Linear Algebra

A and B vectors
1. F(A + B) = F(A) +F(B)
2. scalar. F(A) = F(scalar. A)
If both are true, then it is a linear transformation

Matrix
1. If there is linear transformation on vector A, then a matrix should exist for that transformation
2. F(a1,a2,a3) = F(a1 (1,0,0) + a2(0,1,0) + a3(0,0,1))
	1. F(a1 (1,0,0))+ F(a2(0,1,0)) + F(a3(0,0,1))
		1. a1.F( (1,0,0))+ a2.F((0,1,0)) + a3.F((0,0,1))
	2. Matrix will save this linear transformation on unit vector so that they can be applied to new vector for the transformation
		1. (F1|F2|F3)
			1. As F( (1,0,0)) will give a vector, this data structure is 2D and called a matrix
				1. If this vector is of different length, then this matrix can give different shapes
				2. And this will tie up the shape during matrix matrix multiplication
					1. Matrix(m1,n) * Matrix(n,n2) = Matrix(m1,n2)
3. Dot product is between vectors, and not matrices
	1. We can find angle between them
4. Matrix multiplication is between matrices
5. $L_a(L_b(A))$ = $L_b(L_a(A))$ = $L_c(A)$
	1. This allows taking transpose as linear transformation
	2. There is a matrix associated with $L_a(A)$ and it gives a vector and we apply another transformation on this vector, which gives another vector and there will be another matrix for this transformation
	3. this is matrix matrix multiplication
		1. $(F1*F2)*A$ = $F1*(F2*A)$ 
6. $Matrix^k$ is only possible is matrix is square so that we can do matrix multiplication without shape issue
	1. This does not mean we apply square or power of k to each element
7. Dot product is element wise multiplication of two vectors plus sum. If we don't sum at the end, it is hadamard product
	1. So, dot product is an algorithm
	2. dot product gives similarity so we sum across all dimensions
		1. As we often write .t form so we can use the same api of matrix multiplication instead of calling hadamard and then sum (kind of standardization)
			1. but knowing vector-vector and vector-matrix can help knowing memory patterns and avoiding 0s that can boost speed
	3. If we apply matrix multiplication between a row vector with a column vector, it will work like dot product
8. So, if we a series of equations, we can convert them matrix form and then apply [[Gauss Jordon Elimination]] to find the values of vector which will give RHS
	1. If number of equations < number of unknowns
		1. Infinite solution
	2. equations can be seen as lines and if they don't intersect each other, then we don't have a solution
		1. So, if we have number of equations > number of unknowns, where some equation can be seen as violating constraints
9. $A*x_s=b$
	1. $A*x_n=0$
	2. $A*x_s+ A*x_n=b + 0$
		1. here b is also a vector and not a scalar
	3. So, both vectors are solution
		1. $x_s$ is a solution as well as $x_s+x_n$
			1. multiply $x_n$ with k and that combined vector is also a solution
		2. So, we will have infinite solution if even one vector $x_n$ gives $A*x_n=0$
			1. this ties to number of equations < number of variables
10. There is [[Null Space]], [[Column Space]] and [[Row Space]]



We have [[Gaussian Elimination]] to find values for x that satisfies the equation. We  can have more than 1 solution if determinant is 0. Matrix won't invert in that case. We can take projection using dot product = 0 method on cos component. Inverse is expensive, so we need orthogonal matrices where we can transpose to get inverse. If we can break matrix into multiplication of matrices with special properties, then we can try to get rid of inverse operation. Eigen value is useful for taking power of matrix to tell how transition probability will move the vector on consequsitive multiplication. Eigen values is diagonal and power is directly applied to its elements.
	
---
# References

1. https://math.stackexchange.com/questions/2354047/dot-product-vs-matrix-multiplication-is-the-later-a-special-case-of-the-first
2. https://learning.edx.org/course/course-v1:UTAustinX+UT.5.05x+1T2022/block-v1:UTAustinX+UT.5.05x+1T2022+type@sequential+block@de9876de14394df395423b596b7884d4/block-v1:UTAustinX+UT.5.05x+1T2022+type@vertical+block@016aa13321b74df9adb6cb2c615084e7
3. https://learning.edx.org/course/course-v1:UTAustinX+UT.5.05x+1T2022/block-v1:UTAustinX+UT.5.05x+1T2022+type@sequential+block@aae154ba4c54456cb007c1626383838a/block-v1:UTAustinX+UT.5.05x+1T2022+type@vertical+block@5478ac02bf8a40688c0d9869f27d99a9