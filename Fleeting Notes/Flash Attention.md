202411191230
Status: #idea
Tags:

# Flash Attention

1) Memory is allocated at KV block level instead of asking complete 2 mb memory
	1) lesser fragmentation
	2) for variable length, memory can be requested dynamically
2) Attention score is not on all tokens but calculated at block level and streamed
3) Copy on Write
	1) Copy the kv block for all common tokens into another kv block
		1) predict twice
---
# References

1. https://gatech.instructure.com/courses/516842/external_tools/17731