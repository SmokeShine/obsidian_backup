202509031411
Status: #idea
Tags:

# SGlang

[[vLLM]] are agnostic of the workload while SGlang can advantage from the workload defined
- Use RadixAttention - which is a common prefix tree for system prompts
	- Similar to phd assistant where for next chat, we copy the whole chat history, it can store the previous history in radix tree
	- [[Context Window]] can be as big as [[KV Cache]]. Once the memory is full, it will remove the earlier tokens from the registers. 
		- Now, the context length will be KV cache length
- Compressed finite state machine - 
	- Instead of decoding {, value,:} as 3 tokens, the compiler can decode {value: as one token
---
# References

1. 