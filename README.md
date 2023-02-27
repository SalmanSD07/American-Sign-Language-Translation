# American-Sign-Language-Translation

American Sign Language (ASL) is the primary language used by many deaf individuals in North America, and it is also used by hard-of-hearing and hearing individuals. The language is as rich as spoken languages and employs signs made with the hand, along with facial gestures and bodily postures.

A lot of recent progress has been made towards developing computer vision systems that translate sign language to spoken language. This technology often relies on complex neural network architectures that can detect subtle patterns in streaming video. However, as a first step, towards understanding how to build a translation system, we can reduce the size of the problem by translating individual letters, instead of sentences.

In this notebook, I had train a convolutional neural network to classify images of American Sign Language (ASL) letters. After loading, examining, and preprocessing the data, I had trained the network and test its performance.

In the code cell, the training and test data is loaded.

x_train and x_test are arrays of image data with shape (num_samples, 3, 50, 50), corresponding to the training and test datasets, respectively.
y_train and y_test are arrays of category labels with shape (num_samples,), corresponding to the training and test datasets, respectively.

Visualize the training data

Created a list of string-valued labels containing the letters that appear in the dataset. Then, visualized the first several images in the training data, along with their corresponding labels.

Examine the dataset
Examined how many images of each letter can be found in the dataset.

Dataset has already been split into training and test sets, where x_train and x_test contain the images, and y_train and y_test contain their corresponding labels.

Each entry in y_train and y_test is one of 0, 1, or 2, corresponding to the letters 'A', 'B', and 'C', respectively.

I used the arrays y_train and y_test to verify that both the training and test sets each have roughly equal proportions of each letter.


One-hot encode the data

Labels for each of the letters are encoded as categorical integers, where 'A', 'B' and 'C' are encoded as 0, 1, and 2, respectively. However, Keras models do not accept labels in this format, and we must first one-hot encode the labels before supplying them to a Keras model.

Defining the model

Here defined a convolutional neural network to classify the data.

This network accepts an image of an American Sign Language letter as input. The output layer returns the network's predicted probabilities that the image belongs in each category.

Training the model

After training the model for 2 epochs the training accuracy was 88.91% and validation accuracy was 90%.

Test the model

The model has then been tested and got a significant accuracy of 93.75%.

Visualizing the mistakes

The errors in the prediction was then visualized and has been left for further study of what could possibly went wrong and hoew can this model be improved further
