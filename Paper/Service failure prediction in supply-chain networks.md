202412301341
Status: #paper
Tags:

# Service failure prediction in supply-chain networks

# Motivation
1. Predict probability of failure based on call ping given to the customer before delivery

------

# Research question and objective
1. 

--------
# Strengths
1. High Quality Data
	1. Very little missing value
2. Converts to binary classification instead of multi class
3. Use multi class + association rules (similar to permutation importance) to find important features related to failure type

# Weaknesses
1. Very basic method
	1. Does not compare against other model types
2. Relies on spamming more calls for counter measure
3. Blocking zip codes where refused by customer is high
4. Recalculate route optimization with additional slack time
	1. may not be feasible as it requires recalculating all routes
---------

# Possible gaps and/or inconsistencies
1. Work is siloed to model
	1. Does not tie how model input will work an actual optimization
		1. Could have been easy paper
2. Old Paper

--------

# Future work
1. No Discussion

------
# Short discussion
1. 

-----

# Relevance to your work
1. 

-------
# References

1. https://arxiv.org/abs/1810.09944