202510231700
Status: #idea
Tags: [[AI Engineering]]

# CPU Pinning
 - With CPU scheduling, processes can run on different cores while context switching
	 - NUMA node is memory attached close to CPU
 - This can lead to CPU and GPU on different cores/ numa units and this can increase communication latency
 - If we pin it, CPU will not change cores for the processes and block memory
	 - this is ulimit
		 - can lead to out of memory error if limit is low
	 - CPU wont swap the memory
 - During training, we would not want 1 million pages to be collected, so we increase hugepage
	 - during inference, we should disable hugepage, as it will increase latency
 - Real time priority so that normal processes cannot occupy the CPU
	 - we are starving normal process
 - If there is an interrupt, force the same CPU core to handle it, instead of other core, which can cause cache eviction and cross node communication
 - Disable memory swapping as we cannot allow any memory to be flushed to disk
	 - disable swap devices
 - For checkpoint, batch more data in RAM, before flushing to disk
	 - this can cause stall
 - Disable CPU sleep in bios



---
# References

1. https://learning.oreilly.com/library/view/ai-systems-performance/9798341627772/ch03.html#ch03_pytorch_and_higher_level_ai_frameworks_1757308027909643