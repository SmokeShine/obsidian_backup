202512131642
Status: #idea
Tags: [[Gaussian Elimination]]

# LU Factorization

A= LU
Both L and U have special properties that are upper/lower triangle matrix
- So they have zeros in special places
- This makes L contain another smaller L and U contain another smaller U
	- L and U are split from A and can be cached so if b changes on right hand side, we can still reuse them
	- sometimes, we have to pivot if there is 0 in the upper triangular matrix
- At the end, Ax= b becomes solving L which we know is simple due to Gaussian elimination
- Watch the youtube video
---
# References

1. https://learning.edx.org/course/course-v1:UTAustinX+UT.5.05x+1T2022/block-v1:UTAustinX+UT.5.05x+1T2022+type@sequential+block@90318f3de35d4418ae7b5195edc05b55/block-v1:UTAustinX+UT.5.05x+1T2022+type@vertical+block@f83e27de49614513a64aeb3224a59f4d
2. https://www.youtube.com/watch?v=BFYFkn-eOQk&t=458s