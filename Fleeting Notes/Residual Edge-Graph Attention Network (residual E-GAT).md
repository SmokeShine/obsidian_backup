202403111132
Status: #idea
Tags: [[Graph Attention Network (GAT)]]

# Residual Edge-Graph Attention Network (residual E-GAT)

Encoder
Input - Passed through two fully connected layers and Batch normalization
- (x,y) coordinates
- edge feature (distance from other nodes)
	- Fixed Length
Residual E Gat 
- input to residual e gat 
	- node features and edge features in layer 0
	- updated node features and unchanged edge features in layer 1
- concatenate both node feature of neighbour, previous node feature (l-1) and edge feature and softmax to get alpha for each neighbour
	- size change due to concatenation does not matter as we are trying to get alpha from each neighbour 
	- leaky relu before softmax
- Update only the node features and not the edge features
- Residual 
	-  Weighted sum from all alphas and previous node feature value
	- Mean  from encoded output from each node to create a context vector
		- context vector is graph embedding
Decoder
- Two attention sublayers
	- Multi header attention 
		- for each head, concatenate and connect to a fully connected layer to get 1x1 context vector
	- then use a single head attention with the previous context vector to get a softmax and a pointer
		- single head so that we don't have to use linear layer again to get 1x1 context vector
			- context vector is associated with head + linear, not with probability (may be)
		- this is calculating probability distribution
	- after selecting a next node, context vector is graph embedding + node embedding of selected noded + node embedding of the first selected node and not graph embedding for further decoding
		- graph embedding is updated by node embedding for first selected embedding and previous step selected node embedding
		- for first step, as there is no previous, we use x size learnable vector


---
# References

1. https://www-sciencedirect-com.proxy.bnl.lu/science/article/pii/S092523122200978X