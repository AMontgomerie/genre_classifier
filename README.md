The goal of this project was to attempt to classify music genres from melspectograms of tracks by using neural networks. There are two datasets and two models. A more detailed report of the project can be found [here](https://drive.google.com/file/d/1D8KfViG-MR7UjyeWHBGjieJvQ7Pf3tHv/view?usp=sharing).

# Datasets
There are two datasets, both of which are made up of melspectogram pngs of size 128x1292. The melspectograms were created by downloading 30 second song samples using the Spotify API. The samples were then converted to melspectograms were then generated using librosa.

[The first dataset](https://drive.google.com/open?id=1lLREvqrvjv907NHXm7ExJdUOXUsTO91R) is about 40,000 melspectogram images which represent the following genres: pop, rock, rap, metal, house, r&b, classical, techno, jazz, and folk. [The second dataset](https://drive.google.com/open?id=1Hv9AsEHdx5mKL7o6io_XegeQfVOPjP9g) is made up of over 100,000 spectograms representing a range of heavy metal, punk, and hardcore subgenres. The second dataset also includes additional tabular track data acquired from the Spotify API such as duration, mode, key, etc.

The second dataset is more difficult to classify as there are a larger number of classes and because the classes are much more similar to each other.

The melspectograms are titled with their track ID as given by the spotify API. The labels for the first dataset can be found [in the corresponding csv file](https://github.com/iarfmoose/genre_classifier/blob/master/genre_classifier/spotify_track_preview_data.csv). The labels for the metal subgenre dataset are in the same file as the tabular data which is metal_track_data.csv [inside the zip file for the second dataset](https://drive.google.com/open?id=1Hv9AsEHdx5mKL7o6io_XegeQfVOPjP9g).

The datasets can be downloaded here:
+ [Genres dataset](https://drive.google.com/open?id=1lLREvqrvjv907NHXm7ExJdUOXUsTO91R)
+ [Metal subgenres dataset](https://drive.google.com/open?id=1Hv9AsEHdx5mKL7o6io_XegeQfVOPjP9g)

# Models
## genre_classifier
This is a neural network which uses convolutional and recurrent layers to classify the genres of melspectograms from the first dataset.

The network architecture is based on [Convolutional Recurrent Neural Networks For Music Classification](https://arxiv.org/pdf/1609.04243.pdf) by Keunwoo Choi et al. The CRNN architecture takes an image as input and then passes it through 4 convolutional layers. The output is then passed through a 2 layer GRU and finally softmax. The network is able to achieve an 80% accuracy rate (80% for top 1 accuracy, and 98% top 5 accuracy).

## metal_subgenre_classifier
The model is based on the same CRNN architecture as the genre_classifier. However there is also a 2 layer fully-connected network which takes tabular track data as an input, and whose output is concatenated with the output of the GRU before being passed through a softmax.

The addition of the tabular data slightly improves the accuracy of the model. However, the final accuracy of the model is only 62%, which is lower than the other model (62% top 1 accuracy, but 92% top 5 accuracy). This is probably due to the increased difficulty of classifying similar sub-genres rather than more distinct genre categories.
