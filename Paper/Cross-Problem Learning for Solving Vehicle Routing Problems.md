202409041133
Status: #paper
Tags:

# Cross-Problem Learning for Solving Vehicle Routing Problems

# Motivation
1. Address the inefficiency of training separate models for each vehicle routing problem (VRP) variant by leveraging transferable knowledge across different VRP variants.

------

# Research question and objective
1. Develop a method for cross-problem learning to enhance heuristics training for various VRP variants.
2. Use a backbone Transformer model pre-trained on the Traveling Salesman Problem (TSP) to improve performance on other VRP variants.

--------
# Strengths
1. Utilizes a pre-trained Transformer backbone to transfer knowledge across different VRP variants, improving efficiency
2. Offers both full and adapter-based fine-tuning methods, providing flexibility in training and parameter efficiency.
3. Demonstrates superior performance compared to models trained from scratch.

# Weaknesses
1. complex modularization and fine-tuning
2. depends on quality of the pre-trained Transformer model
---------

# Possible gaps and/or inconsistencies
1. One shot performance on new variants may be useful if there is shared knowledge

--------

# Future work
1. 

------
# Short discussion
1. 

-----

# Relevance to your work
1. Shared knowledge across variants with pretraining similar to [[Attention, Learn to Solve Routing Problems!]]

-------
# References

1. 