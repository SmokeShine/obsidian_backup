202409301215
Status: #idea
Tags:

# Reparameterization Trick

If we are sampling in Variational Autoencoder to get new images, we cannot use it for backpropogation. So, we move mean and standard deviation and use random error between 0 and 1. Now, the backpropogation does not depend on sampling. The random error will help in avoiding overfittiing, same as the difference between batches.

---
# References

1. 