202501211119
Status: #idea
Tags: [[Long Short-Term Memory (LSTM)]]

# Forget Gate

![[Pasted image 20250121112344.png]]

- Forget gate is simple sigmoid on previous hidden state. If its value is 0, cell state is not used. It is element wise multiplication.
- If its value is 1, then complete cell state is used. The scaled x from [[Input Gate]] get element wise added with cell state. 
- Forget gate is sigmoid. So, values in cell state can be seen discount factor. 

- [[Transformer]] do not have forget gate. So, the denominator in [[Attention]] can get memory overflow over long [[Context Length]]. [[RNN]] forget via compression, while [[Long Short-Term Memory (LSTM)]] have a dedicated forget gate

---
# References

1. https://www.pluralsight.com/resources/blog/guides/introduction-to-lstm-units-in-rnn