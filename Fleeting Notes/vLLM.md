202411191157
Status: #idea
Tags: [[LLM Inference]]

# vLLM

- Main class is LLM
- Most commonly used is generate function
	- This is async, so there is a queue
	- After all requests in the queue, call scheduling function
- The requests are added LLM engine class
	- this has an optimizer which will try to schedule to minimze cost
	- After this is done, there is a step function, which will call executor class
		- executor will execute the model 
			- this will call rpc, which will trigger the run the method in worker node
- The worker node will have a class for model runner and observability
	- the input will be input text along with KV cache to this function
	- Now, this will be passed to execute model, which will decide the kind of attention that needs to be used for the input and kv cache
	- now, the model is executable - we have everything input text, kv cache and attention algorithm and we can wrap this in nn.module
		- the default for nn.module in pytorch is forward
		- We then pass all the three things and load the llama class which will have forward implemented
			- each model can have different sampling and calculating logits technique
				- the sampling will return the next token
	- now, forward is called and we get logits
- vLLM can be compared to [[SGlang]] with throughput and latency
---
# References

1. 