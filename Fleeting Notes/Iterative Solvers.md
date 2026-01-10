202512281315
Status: #idea
Tags: [[Gram Schmitt Orthogonal Process]]

# Iterative Solvers

For iterative solvers, we should not wait for cubic time and should be able to stop it in between. With [[Gaussian Distribution]], we have mean and covariance, and we can stop it after seeing few number of data points. As we see more data points, our [[Posterior]] will update and will still be Gaussian distribution. So, by seeing one point at a time, I still get Gaussian with mean and covariance and can stop in between.  The math is similar to [[Gram Schmitt Orthogonal Process]] to get the iterative updates for covariance matrix

So, this iterative solver can be seen as dataloader that decomposes the matrices for faster calculations. 

Instead of selecting one vector, we can take a weighted sum of vectors. So, this can be seen [[Policy]] for selecting which rows to pick. It can be random and we need to do book keeping how the selection happened.

In [[Gaussian Distribution]], [[Posterior]] still has matrices for A. So, if we can decompose this matrix with [[Cholesky Factorization]]/ [[LU Factorization]]/[[QR Factorization]]/ [[Singlular Value Decomposition SVD]], it will become easier to write code to get mean and covariance of posterior distribution even with iterative method. If we do [[Stochastic Gradient Descent (SGD)]] only on projections which were not present in previous seen rows, and only on new information, it is called [[Conjugate Gradients]]. As our gradient descent now depends on new information, I don't need to see all data but can see the data from a batch to make an update.


---
# References

1. https://www.youtube.com/watch?v=BtFMic77Nes&list=PL05umP7R6ij0hPfU7Yuz8J9WXjlb3MFjm&index=5