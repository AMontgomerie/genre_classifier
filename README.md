# genre_classifier
A neural network which uses convolutional and recurrent layers to classify the genres of melspectograms.

The melspectograms were created by downloading 30 second song samples using the Spotify API. The samples were then converted to melspectograms were then generated using librosa. The dataset is about 40,000 melspectogram images which represent the following genres: pop, rock, rap, metal, house, r&b, classical, techno, jazz, folk.

The network architecture is based on [Convolutional Recurrent Neural Networks For Music Classification](https://arxiv.org/pdf/1609.04243.pdf) by Keunwoo Choi et al. The CRNN architecture takes an image as input and then passes it through 4 convolutional layers. The output is then passed through a 2 layer GRU and finally softmax. The network is able to achieve an 80% accuracy rate.
