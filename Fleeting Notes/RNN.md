202311291445
Status: #idea
Tags: [[Seq2Seq]]

# RNN

1. Input data is not iid and hence there is no statistical assumption
2. Suffers from [[Vanishing Gradient]] and [[Exploding Gradient]]
3. We can predict the continuous coordinate of next city during inference, but it is possible that the predicted coordinate is no more an input coordinate

---
# References

1. https://stats.stackexchange.com/questions/460794/iid-assumption-in-sequential-supervised-learning
2. https://arxiv.org/abs/1506.03134