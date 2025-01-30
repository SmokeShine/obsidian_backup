202403111130
Status: #idea
Tags: [[Graph Neural Network (GNN)]]

# Graph Attention Network (GAT)

1. Message
2. Aggregation
	1. multi headed attention to know which neighbour is more important
		1. concat if cascading multiple attention block
		2. mean instead of concat for final attention block
	2. invariant to permutation

![[Pasted image 20250130213030.png]]

---
# References

1. https://www.youtube.com/watch?v=247Mkqj_wRM&list=PLoROMvodv4rPLKxIpqhjhPgdQy7imNkDn&index=21
2. https://epichka.com/blog/2023/gat-paper-explained/