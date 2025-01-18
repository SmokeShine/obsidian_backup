
202501141428
Status: #idea
Tags: [[Loss Function]]

# Classifier Free Guidance

1. For predicting P(y/x), if we can get P(x), then we can use $$\begin{align} \gamma * log P _\theta (\text{next audio token}/\text{text,previous audio}) * \\
(1-\gamma) log P_\theta (\text{next audio token/previous audio}) \end{align}$$
3. This is to say that sometimes if we don't have text, we can still use it with a mixture of conditional and unconditional probabilities 
---
# References

1. 