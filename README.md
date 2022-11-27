# VAE
Variational autoencoder
The standard autoencoder can have an issue, constituted by the fact that the latent space can be irregular [1]. This means that close points in the latent space can produce different and meaningless patterns over visible units.

One solution to this issue is the introduction of the Variational Autoencoder. As the autoencoder, it is composed of two neural network architectures, encoder, and decoder.

But there is a modification of the encoding-decoding process. I will explain all the steps:

We encode the input as a distribution over the latent space, instead of considering it as a single point. This encoded distribution is chosen to be normal so that the encoder can be trained to return the mean matrix and the covariance matrix.
In the second step, we sample a point from that encoded distribution.
After, we can decode the sampled point and calculate the reconstruction error
We backpropagate the reconstruction error through the network. Since the sampling procedure is a discrete process, so it’s not continuous, we need to apply a reparameterisation trick to make the backpropagation work:
