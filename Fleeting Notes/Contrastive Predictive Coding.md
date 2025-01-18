202501141445
Status: #idea
Tags:

# Contrastive Predictive Coding

1. Identify true sample from random sample using CNN
2. run an autoregressive model and get a context vector at time t. Now, use this context vector to generate next time steps
	1. each input may have some noise and signal. Using context vector/summarization of history we are trying to extract the signal and say if it is useful for the next time step.
	2. density ratio = probability of next token generated given context/ probability of next token generated
---
# References

1. https://paperswithcode.com/method/contrastive-predictive-coding
2. https://www.youtube.com/watch?v=zNKMHj1eLa0