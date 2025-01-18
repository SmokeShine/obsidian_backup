202401311220
Status: #idea
Tags: [[Pointer Network]]

# Pointer Network Implementation

# Data Creation
1. Label data using Held-Karp heuristic algorithm
2. No depot creation
3. Create random points for fixed batch size from 1x1 square
	1. Could not fix the issue with variable length batch size

# Model
## Encoder
1. RNN takes (x,y) coordinates as input and roll over each time step
2. For each time step, we store the output
3. hidden state of last step becomes the hidden state of the decoder
## Decoder
1. (0,0) as input start token
2. Decode one state
	1. Attention
		1. output from decoder with attention from encoder outputs
		2. find index for the max value
	2. index is used as output label
	3. (x,y) for coordinate of that index used as input for next time step
	4. Loops are possible
3. Stop decoding when all cities are visited

# Training
1. Labels are matched for calculating the loss
2. Categorical cross entropy
	1. instead of one label with one prediction, we have one label vs log probabilities of all output states

---
# References

1. https://discuss.pytorch.org/t/categorical-cross-entropy-loss-function-equivalent-in-pytorch/85165/4
2. https://github.com/SmokeShine/Pointer-Network
3. https://arxiv.org/abs/1506.03134

------

