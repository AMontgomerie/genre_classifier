There are two models with similar architectures and two datasets. The first model was trained to classify broad genre categories, and the second was trained to classify similar sub-genres using a dataset of heavy-metal tracks.

# genre_classifier
This is a neural network which uses convolutional and recurrent layers to classify the genres of melspectograms.

The melspectograms were created by downloading 30 second song samples using the Spotify API. The samples were then converted to melspectograms were then generated using librosa. The dataset is about 40,000 melspectogram images which represent the following genres: pop, rock, rap, metal, house, r&b, classical, techno, jazz, and folk.

The network architecture is based on [Convolutional Recurrent Neural Networks For Music Classification](https://arxiv.org/pdf/1609.04243.pdf) by Keunwoo Choi et al. The CRNN architecture takes an image as input and then passes it through 4 convolutional layers. The output is then passed through a 2 layer GRU and finally softmax. The network is able to achieve an 80% accuracy rate.

# metal_subgenre_classifier

The model is based on the same CRNN architecture as the genre_classifier. However there is also a 2 layer fully connected network whose output is concatenated with the output of the GRU before being passed through a softmax.

The dataset is made up of over 100,000 spectograms representing a range of heavy metal, punk, and hardcore subgenres. The goal was to see if these subgenres could be accurately classified based on melspectogram images. The tabular track data was added to improve the accuracy of the classifier.

The model is able to achieve an accuracy of about 62%, which is lower than the previous model. This is probably due to the increased difficulty of classifying similar sub-genres rather than more distinct genre categories.
