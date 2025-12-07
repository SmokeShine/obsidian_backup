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
---
# References

1. https://math.stackexchange.com/questions/2354047/dot-product-vs-matrix-multiplication-is-the-later-a-special-case-of-the-first
2. https://learning.edx.org/course/course-v1:UTAustinX+UT.5.05x+1T2022/block-v1:UTAustinX+UT.5.05x+1T2022+type@sequential+block@de9876de14394df395423b596b7884d4/block-v1:UTAustinX+UT.5.05x+1T2022+type@vertical+block@016aa13321b74df9adb6cb2c615084e7