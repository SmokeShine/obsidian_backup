202512242104
Status: #idea
Tags:

# Change of Probability Density Function

- Probability will not change

$F_Y (y) = F_X (g^-1(y))$

Differentiate both sides now. Differentiating CDF will give PDF. Because of chain rule, we need to decide whether we should differentiate by dx or dy on both sides and that will give the formula

![[Pasted image 20251224212839.png]]

In the formula, inverse is just reading value from X domain

Assume x be a uniform number between 0 and 1 is my pdf. Its integration will give 1. So, it is valid pdf on 1/b-a = 1/1-0 = 1.

Assume pdf of Y is unknown. So, integral Y * dy = 1 * dx
but we know $dy/dx = d (x^2)/dx$
$dy/dx=2x$
$dy=2xdx$
but we know $1.dx=pdf$
=> $F=dx/dy$
=>$F = 1/2x$
$=>F=1/2(\sqrt[2]{y})$
Now, all the variables are changed into y



---
# References

1. https://stats.stackexchange.com/questions/239588/derivation-of-change-of-variables-of-a-probability-density-function