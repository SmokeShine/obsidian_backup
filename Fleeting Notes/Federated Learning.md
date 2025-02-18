202501191326
Status: #idea
Tags:

# Federated Learning

- For data privacy, all data is stored locally and trained locally
	- When mobile is not in use or charging
	- Local model can work even when offline
		- Good latency
	- Model is initialized centrally and each client receives a copy of the model
- Centralized model receives the gradient updates
	- A model checkpoint is sent to client with configuration
		- Clients use this model to train with their local data
	- Uses [[Secure Aggregation Principle]]
	- Could be poisoned
	- some clients may use the model more and hence send more updates than others
		- this can create imbalance as the model is optimized for high frequency users
	- heterogeneous clients base, so data generated can be thought of coming from different distributions and model is assuming there is only one distribution
		- model will have convergence issue now
			- some clients will think model is great while others will feel the model is useless, leading to more imbalance
				- If there is bias in data, this process will increase it further
				- If there are new clients, then the distribution is not representative anymore
			- Cross silo with few major clients like Banks/Hospitals may work well
				- would require better encryption logic as [[Secure Aggregation Principle]] can be compromised with drop out easily; so it would be better to the server knows the identity to remove the protocol beforehand
				- Training locally would be computationally expensive as there is massive data while server is merely acting like a message queue
- Centralized model is updated and updated model is shared back with clients
- For analyzing model performance, clients can share the accuracy of their model without any gradient update and the centralized server can then use this to estimate a proxy for model performance
- Google collects this data using usage and diagnostics
- tff.learning in tensorflow is used to convert a normal model to federated
- is peer-to-peer similar to crypto mining?
- [[Federated Empirical Risk Minimization]]
- Convergence guarantee using [[B-Dissimilarity]]
- Improve communication
	- Use [[Dimensionality Reduction]] to create a bottleneck and train the model from it
	- Compress all the updates using a known compression algorithm
		- [[Sparsification]] update only selected weights and freeze others
		- [[Quantization]] to 4 bit
		- [[Dropout]]
- Surface of attack
	- access to a clients device
		- compromise the data
		- compromise the model
	- access to network
	- access to server
		- aggregated metrics
	- access to a released model
- Only used for Supervised Learning
	- not for Unsupervised Learning
	- not for [[Reinforcement Learning]]

- in case of spam/scam, waiting for centralized model to collect data and train could take a lot of time when the clients are already tagging the labels
	- messages can have sensitive data and financial information
	- if a client has a broken system, it cannot be detected as outlier for removal
		- masking can be inferred of other system
---
# References

1. https://www.analyticsvidhya.com/blog/2021/05/federated-learning-a-beginners-guide/
2. https://drive.google.com/file/d/1QGY2Zytp9XRSu95fX2lCld8DwfEdcHCG/view?pli=1
3. https://pair.withgoogle.com/explorables/federated-learning/
4. https://arxiv.org/pdf/1902.01046
