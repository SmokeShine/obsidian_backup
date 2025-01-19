202501191544
Status: #idea
Tags:[[Federated Learning]]

# Federated Averaging

1. [[Stochastic Gradient Descent (SGD)]] steps on customer device
	1. Customer is using [[backpropagation]] to reduce loss
	2. Sends the weight changed during local training
2. Server do weighted average
	1. what are the weights
		1. Number of samples selected/total number of samples
3. FedProx limits gradient updates similar to fix in [[Exploding Gradient]]
	1. do partial participation instead of dropping
---
# References

1. https://drive.google.com/file/d/1QGY2Zytp9XRSu95fX2lCld8DwfEdcHCG/view?pli=1
2. https://www.rtinsights.com/federated-averaging-the-backbone-of-federated-learning/