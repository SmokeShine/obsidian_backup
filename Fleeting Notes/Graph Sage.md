202403111155
Status: #idea
Tags: [[Graph Neural Network (GNN)]]

# Graph Sage


1. Message
2. Aggregation - two stage
	1. aggregate from neighbours
	2. aggregate from node 
		1. without this, the previous hop values of node will be lost and not used for updating the embedding
	3. aggregation type
		1. mean - same as [[Graph Convolutional Network (GCN)]]
		2. minpool/maxpool - focussing only on one neighbour
		3. LSTM on embeddings of neighbours
			1. not invariant, so need to apply multiple times
				1. can this be converted to attention???
					1. yes,  [[Graph Attention Network (GAT)]] is same
					2. ==***why not hop also have attention? closer are more important, but cant ignore farther connections as well***==
							1. this is done in GAT
						1. can be LSTM, as hopping inherently has a sequence
						2. how to use this mathematically in equation?
	4. L2 normalization at each hop
		1. vectors come at same scale and have same L2 norm
		2. may be performance improvement
---
# References

1. https://www.youtube.com/watch?v=247Mkqj_wRM&list=PLoROMvodv4rPLKxIpqhjhPgdQy7imNkDn&index=21