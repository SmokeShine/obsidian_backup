202411191151
Status: #idea
Tags: [[Deep Learning]]

# Perplexity

- Multiply probability of generating tokens in a sentence
	- We multiple probability of each token given previous token
	- but now we cannot compare two sentences as they can have different length
	- We can normalize this by dividing by number of words
		- But this is not done
		- if one token has 0 probability, it should be infinitely surprised
			- sum is non zero and hence the definition breaks
	- We can instead use geometric mean which takes nth root of multiplication
		- Perplexity is reciprocal of the above
		- if one token has 0 probability, it will be infinitely surprised
			- 1/0 = infinity
---
# References

1. https://medium.com/nlplanet/two-minutes-nlp-perplexity-explained-with-simple-probabilities-6cdc46884584