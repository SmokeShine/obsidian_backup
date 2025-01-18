202408251649
Status: #idea
Tags:

# New Ideas

- one branch predicts the sequence
	- second branch predicts start and end of token given a vehicle
	- similar to parts of speech tagging
- one model assigns customer to vehicles
	- second model use this assignment to generate routes and enforce constraints
- order of dispatch is fixed
- pickup - delivery pairing 
	-  ???
		- VRP with infinite capacity is TSP - this is what papers are doing and hiding within fine prints 
- Use GNN tokens
- convert dynamic programming to DL
- using GNN tokens to replace one opt in TSP
- treat inference as time series and predict token as exception events
- GAN
	- generator create route
	- discriminator will tell whether the route is feasible or not
- if constraint is violated, add a penalty multiplier
	- Customer assigned to multiple vehicles
		- add penalty multiplier
	- vehicles assigned to multiple customers
	- subtours
- Seq2Seq decoding is k means clustering. It is a venn diagram where masking is used to removing overlapping. As it is homogenous, it does not matter which circle is selected first, nor the number of circle. It will matter in heterogenous.
- Using time matrix and time limit on heterogenous VRP
	- Model on heterogenous paper. Fleet size is fixed
	- Time matrix and time limit are used only in decoder
	- Can use time matrix to mask
		- in that case, some customers may not be visited
			- how do we know all customers can be visited with the given capacity?
				- Re read the paper
		- Use penalty on exceeding time limit, this will help in always generating feasible routes

---
# References

1. 