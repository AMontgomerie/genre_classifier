# genre_classifier
A neural network which uses convolutional and recurrent layers to classify the genres of melspectograms.

The melspectograms were created by downloading 30 second song samples using the Spotify API. The samples were then converted to melspectograms were then generated using librosa.

The network architecture is based on [Convolutional Recurrent Neural Networks For Music Classification](https://arxiv.org/pdf/1609.04243.pdf) by Keunwoo Choi et al.
