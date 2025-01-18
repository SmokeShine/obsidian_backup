202311291134
Status: #idea
Tags: [[Pointer Network]]

# Seq2Seq

1. Seq2Seq encodes input data using [[Attention]] into a single [[Context Vector]] and use in each decoding step
2. Output labels needs to fixed beforehand - argmax(one hot encoding all words) can be converted to a label
	1. For example, in a trained model, we are predicting to go to point 20, when the input was between point 1...7. The dictionary on which softmax is applied is fixed for the trained model
3. It requires knowing the output dictionary in advance which takes a lot of memory in GPU
	1. Memory = model + gradients + values for accelerating optimizer + dictionary

---
# References

1. https://arxiv.org/abs/1506.03134