202501191650
Status: #idea
Tags: [[Federated Learning]]

# Differential Privacy

1. Learn from the group without learning anything about individual
	1. if one client performance can be guessed by observation, then an observer on final centralized model can infer the private data
	2. Clip updates to a value 
	3. Add noise
	4. Then average
	5. Use the average to update the centralized model
3. Train the model by removing some customers by assuming they may be dropped
	1. so not all customers are selected for training rounds
		1. similar to assuming that there is 1 attacker every round and model should become robust
---
# References

1. https://drive.google.com/file/d/1QGY2Zytp9XRSu95fX2lCld8DwfEdcHCG/view?pli=1