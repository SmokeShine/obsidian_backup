202501191329
Status: #idea
Tags: [[Federated Learning]]

# Secure Aggregation Principle

1. Server received encrypted gradient updates from each customer
2. After aggregation, it can decrypt, so it does not know individual gradient updates
3. Use [[Zero Sum Protocol]] 
	1. all participants cooperate with other other
		1. Bottleneck
		2. Pairwise Masking vector generated is as big as the number of parameters of the model
			1. Quadratic
			2. If some customers drop out, then masking will not get cancelled and server would know the details
		3. When aggregated, this masking will cancel each other
	2. individual customer data cannot be decrypted
	3. after aggregation, server can do decryption

---
# References

1. https://www.analyticsvidhya.com/blog/2021/05/federated-learning-a-beginners-guide/
2. https://www.linkedin.com/pulse/secure-aggregation-top-federated-learning-same-faces-blurred-ayari/
3. https://research.google/blog/federated-analytics-collaborative-data-science-without-data-collection/