202505141130
Status: #idea
Tags: [[Neural Combinatorial Optimization]]

# Hypergraph

Take a graph, split it into multiple segments. Reconstruct small graphs allows some nodes to be overlapped by each other

These common nodes are called. [[Hyperedges]]

In this paper, hyper graph looks like a subgraph or a segment. It is frozen and only the isolated nodes are connected to this segment to get the final solution. Instead of [[One-opt]] swap, here, the number of isolated nodes could be many. So, the model is trying to learn which nodes to swap during destruction and reconstruction. But which nodes should be selected from the hyper graph? only the end points?

This is similar to [[Heatmap]] where we think of best nodes for the next sample, but instead this is where to split.

---
# References

1. https://arxiv.org/pdf/2502.16170