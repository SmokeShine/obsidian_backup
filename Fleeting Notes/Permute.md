202510211533
Status: #idea
Tags:

# Permute

- B,N,M,D 
	- this is a vector of size D, repeated M times
		- this is a matrix
	- This matrix is repeated N time
	- It is then repeated B times
- if we convert it to B * N, M, D, then we can M as number of tokens like we see in RNN
	- and then we apply attention on tokens
- We can flatten B * N * M vectors 
- Now, when we permute, the indexing will depend on permute order, as in it will count till M
	- but when we look at the original flatten, the order will now change
	- permute is a verb. so, it means shuffling the flatten order based on new indexes
		- this shuffling is still a map
			- we need to call contiguous, else when we look at memory, it will look fragmented
		- So, B,N,M,D can be seen as a normal array and B,N,M,D can be seen as additional pointers like we see in circular queue
---
# References

1. 