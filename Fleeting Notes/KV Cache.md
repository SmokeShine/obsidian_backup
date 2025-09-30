202509022204
Status: #idea
Tags: [[LLM Inference]]

# KV Cache

- Q
- K 
- V
- All three are derived from X. These are not learned weights, but Q= X.Wt, where X is current token
- Q.KT is a dot product and a scalar for each token. So, for each previous word, we have a scalar value
	- q_t = token * W_q
	- k_t = token * W_k
	- v_t = token * W_v
	- Now, store k_t and v_t in cache
	- then get score = ( q_t * complete K cache ) complete V cache
- Then all K cache are put together in memory
- Similarly, all V cache are put together is memory
- But, K and V interleaved in same block, such that we get corresponding K and V in the same block in one shot
---
# References

1. 