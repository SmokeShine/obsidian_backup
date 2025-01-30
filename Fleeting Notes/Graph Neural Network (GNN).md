202403111129
Status: #idea
Tags:

# Graph Neural Network

Graphs are non grid, have no ordering of nodes/sequence, nodes/edges have multiple attributes, can expand/shrink over time

- Can be seen as [[RNN]] but instead of time steps, we aggregate data in hidden state from neighbours and call in [[Message Passing]]

GNN Layer -  Linear > Batchnorm > dropout > activation > attention > aggregation

So, message and aggregation are not together.

Number of layers = number of hops; 

1. Node Embeddings -  a function that converts the whole graph into d Dimensional embeddings where similar nodes are close to each other
	1. Deep Walk
	2. Node2Vec
	3. matrix factorization
2. GNN - Take graph, apply multiple layers of non linear transformation
	1. Sharing of parameters for each hop during aggregations
		1. take the messages from children and aggregate them
	2. Generate embeddings for new unseen
	3. Use node features
	4. Local Neighbourhood aggregation
		1. connection from each neighbour can be aggregated to get the final embedding
		2. large hopping distance will make all nodes have the same values
		3. average the embeddings (after applying multiplying with trainable weights) from each neighbour and add to node embedding (another trainable weight layer here)
			1. after averaging and summation, non linearity can be applied 
3. Adjacency matrix cannot be directly used as input
	1. order of input sequence can change
	2. matrix can be very big
	3. number of samples = len(adjacency matrix); not enough data and will cause overfitting
4. Train on a batch of nodes; control epoch
	1. use the learnt weight to get embeddings even for new unseen ones

5. randomly sample a node for message passing or select two nodes neighbours for creating the embedding
	1. embedding are similar
6. Splitting data into test/train/valid
	1. computing embeddings on entire graph, but train only selected nodes
	2. break the edges, and create independent graph, create embeddings on individual graphs instead of entire graph

---
# References

1. https://www.youtube.com/watch?v=F3PgltDzllc&list=PLoROMvodv4rPLKxIpqhjhPgdQy7imNkDn&index=17
2. https://www.youtube.com/watch?v=1A6VoEkQnhQ&list=PLoROMvodv4rPLKxIpqhjhPgdQy7imNkDn&index=23
3. https://www.youtube.com/watch?v=ewEW_EMzRuo&list=PLoROMvodv4rPLKxIpqhjhPgdQy7imNkDn&index=25