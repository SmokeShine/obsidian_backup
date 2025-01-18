202311291146
Status: #idea
Tags: [[Literature Review]]

# Pointer Network

1. Same as Seq2Seq but uses attention as pointer to input sequence
	1. for decoding the next step, softmax is required in seq2seq which requires to know the complete label dictionary before hand. So, decoding the next step is the problem.
2. Can be used for variable output length
	3. instead of decoding, whatever is the max softmax on input, go to that point
		1. so we are using dictionary of input, which is always available at input
		2. inference always respect to point to input point
	4. between decoding step, only hidden state is passed.
3. Seq2seq needs to know about the output label dictionary before hand. Pointer network does not need to.
4. If the sequence of vehicle is an input, the vehicles are from same distribution and hence decoding can work
---

Data
Input - sequence of vectors 
	- 2d coordinates
Label Data
- Held Karp Algorithm heuristics

Network
- Single LSTM Layer
	- 256/512 hidden units
- SGD
	- learning rate 1.0
- Gradient Clipping 2.0
- Batch Size 128
- Random Uniform weight initialization (-0.08 to 0.08)
- Epoch 10 to 20
- Sample Size 1 million
- Sampling - sampled uniformly from 1x1 square area

Tour Length 

## Failure Rate
- City is repeated
- City is ignored

## Generalization
1. Trained on 5-20 
2. Generalized on 25/30/40
	1. 25 - perfect
	2. 30 - good
	3. 40+ - breaks
---
Input Network - simple RNN with context vector as hidden state of last time step
Output Network -  takes input token (embedding/random values) and hidden state

Subtour elimination with [[Fleeting Notes/Beam Search]]

> Pointer network performs better than seq2seq and seq2seq+attention even on "fixed size input"

---
# References

1. https://arxiv.org/abs/1506.03134