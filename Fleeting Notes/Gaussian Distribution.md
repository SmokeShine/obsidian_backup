202512251955
Status: #idea
Tags: [[Probabilistic Machine Learning]]

# Gaussian Distribution

- Preferred because it ties with linear algebra cleanly
- When we add two Gaussian, it is another Gaussian
	- Means adds
	- Variance - ?
- When we multiply pdf of two Gaussian, it is another Gaussian
- Adding a vector to Gaussian distribution is similar to adding vector to the mean
- Multiplying a matrix with a Gaussian is another Gaussian
- In the lecture, prof is showing how to create pdf by combining two Gaussian, and the array is because the Gaussian are multi variate
- For a Gaussian with multiple variables, multiplying with matrix can be used to slice one variable and it becomes pdf
	- so pdf which is integral becomes reading values from the matrix
	- Ax gives pdf. So, if Gaussian has 2 dimensions, then the vector can be written as
$\begin{pmatrix}1 & 0\end{pmatrix}\begin{pmatrix}x1\\ x2\end{pmatrix}$
=> x1 is now mean
=> variance is with $A.\sum.A^T$
$\begin{pmatrix}1 & 0\end{pmatrix}\begin{pmatrix}\sigma_{11} & \sigma_{12}\\ \sigma_{21} & \sigma_{22}\end{pmatrix}\begin{pmatrix}1\\ 0\end{pmatrix}$

=> $\sigma_{11}$
$A=\begin{pmatrix}1 & 1\end{pmatrix}$ is adding two Gaussians

- P(X| Ax=y) can be read as probability of X given the data we can fit with labelled y
	- This also has a formula for mean and variance that is also Gaussian
		- It is for random variable X
	- So, y mean can be found from multiplying A with x
	- This can be also be seen as Bayes theorem

---
# References

1. https://www.youtube.com/watch?v=CXCNoAw3YYM&list=PL05umP7R6ij0hPfU7Yuz8J9WXjlb3MFjm&index=3