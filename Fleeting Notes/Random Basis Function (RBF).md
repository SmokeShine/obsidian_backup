202512311318
Status: #idea
Tags: [[Kernel Trick]]

# Random Basis Function (RBF)

- Going input data to a higher dimension so that it becomes linear separable


$e^{-\frac12\left\Vert x_{i}-x_{j}\right\Vert^2}$


So, if we have two rows of data and apply RBF on them, it would be same applying infinite combination of features on them.

Because it works on two vectors, we will have to create a cross table  called gram matrix between every combination of two vectors.  So, it has a scaling problem if there are 1 million rows.

So, if we have limited data, we can select the appropriate kernel to fit the data


---
# References

1. https://www.youtube.com/watch?v=tV5X77lGYP4
2. https://www.youtube.com/watch?v=Q0ExqOphnW0