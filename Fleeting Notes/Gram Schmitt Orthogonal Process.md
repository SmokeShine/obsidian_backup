202512221417
Status: #idea
Tags:

# Gram Schmitt Orthogonal Process

Take two vectors A and B (unit vector) and they have an angle between. 
- Take A cos $\theta$ will be component of A
- Dot product |A||B|cos $\theta$ = |A|cos $\theta$
	- but this is a scalar, not a vector, multiply with direction of B
	-  |A|cos $\theta$  * $\begin{pmatrix} 1 \\ 0 \end{pmatrix}$
	- This is base
	- Component vertically will be A -  |A|cos $\theta$  * $\begin{pmatrix} 1 \\ 0 \end{pmatrix}$ 
		- using vector addition property
- At the end, make both components of length 1 but dividing by their length
	- so, orthogonal vector will become [[Orthonormal Vectors]]

![[Pasted image 20251222145102.png]]

A = QR
Q.T * A = Q.T * Q * R
=> Q.T * A = Identity * R
So, now we have a way to calculate R


---
# References

1. https://learning.edx.org/course/course-v1:UTAustinX+UT.5.05x+1T2022/block-v1:UTAustinX+UT.5.05x+1T2022+type@sequential+block@8db8dbddcb734e2ead4d5a74b828e664/block-v1:UTAustinX+UT.5.05x+1T2022+type@vertical+block@e9356d78caec45bda799d2b7acc2f64c
2. https://www.youtube.com/watch?v=BtFMic77Nes&list=PL05umP7R6ij0hPfU7Yuz8J9WXjlb3MFjm&index=5