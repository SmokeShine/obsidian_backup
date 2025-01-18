202311291149
Status: #idea
Tags: [[Seq2Seq]]

# Attention

[[Context Vector]] with relative importance of input.
Variable length output by padding to maximum length. During training, put a mask saying it is 0 and it will return 0 during inference. Post process.

---
# References

1. https://medium.com/@b.terryjack/deep-learning-the-transformer-9ae5e9c5a190
2. https://github.com/keras-team/keras/issues/5389#issuecomment-279555319