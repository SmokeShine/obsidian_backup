202512271242
Status: #idea
Tags:

# Joint Distribution

![[Pasted image 20251227124240.png]]

Because it is Gaussian, x1 mean will be adjusted because of x1 formula. It will move on coordinate axis by +v1 but mean will just scale. Variance will not change, so we use $\sigma^2$

Or we can see x1 as [[Change of Probability Density Function]] and use [[Jacobian Matrix]] to get the pdf of LHS. Jacobian is always used when we are using a change of variable. Even though Jacobian can be seen as derivative, the matrix A itself stores scaling factor for each unit vector. So, we can replace the Jacobian with the matrix A. Or, we can calculate the Jacobian and put that in [[Change of Probability Density Function]] to get pdf in the new domain from x1,x2,x3 to v1,v2,v3. In this way, we don't have to remember property that Gaussian mean will adjust and variance will not change. Here, the important thing to not is p(x2) formula will convert to a Gaussian formula which allows multiplying and removes the bracket of p.

---
# References

1. https://www.youtube.com/watch?v=CXCNoAw3YYM&list=PL05umP7R6ij0hPfU7Yuz8J9WXjlb3MFjm&index=3