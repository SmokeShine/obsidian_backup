202403111602
Status: #idea
Tags: [[Graph Neural Network (GNN)]]

# Issues with GNN


Oversmoothing
Similar receptive field = similar nodes. So, if there are too many hops, the receptive field will start looking similar for a lot of nodes which decreases its expressive power

Solution
1. make each hop linear layer to be deep themselves
2. Add additional attribute information to each nodes
3. skip connections (skip some layers to connect ahead)
	1. these connections can help differentiate nodes based on past layer nodes
	2. residual connection is a type of skip connection
4. pre processing and post processing each hop with linear layers

---
# References

1. https://www.youtube.com/watch?v=ew1cnUjRgl4&list=PLoROMvodv4rPLKxIpqhjhPgdQy7imNkDn&index=22