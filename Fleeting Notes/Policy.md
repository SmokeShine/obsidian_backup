202310232346
Status: #idea
Tags: [[Agent]]

# Policy

Mapping from state to action

1. Can be deterministic
2. Can be stochastic
	1. Useful for random exploratory behaviour
	2. Distribution of actions given a state (s)
3. Does not depend on time because of Markov property that state holds all information for the future

For a VRP, decoder policy should only depend on depot and previous city, and current load of vehicle. And should be independent of intermediate step. In such a case, policy will always take the same decision and is not impacted by intermediate cities
	- if it is not conditioned on current load, this allows for sampling during decoding time, if we always pass a static embedding for all decoding steps.
		- We select a city at random, we know depot, we sample the rest of the trajectory. We do it multiple times, and select the one with the least length
		- if we use encoder embedding, we are conditioning on all cities through attention, and this is incorrect as now the decoder is conditioned on intermediate nodes apart from depot and previous node

---
# References

1. https://www.youtube.com/watch?v=2pWv7GOvuf0
2.  https://www.youtube.com/watch?v=lfHX2hHRMVQ
3. https://openreview.net/pdf?id=4pRwkYpa2u