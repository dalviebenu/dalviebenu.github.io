---
title:  "Neural Network based alphabet recognizer"
permalink: /projects/neural-network/
layout: page
---

## What is the Neural Network based alphabet recognizer?
This project was created as the final project for the course "Artificial Intelligence and Applied Methods" at the KTH Royal Institute of Technology.
The goal of the project was to create a neural network that could read handwriting and convert it into text on the computer. The neural network was trained using the
MNIST dataset, which contains 60,000 training images and 10,000 test images of handwritten digits. The final model was able to achieve a 95% accuracy on the test set.

## How does it work?
The solution is split into two parts: an image processing part and the actual model. The image processing part is responsible for splitting up the sentence
into individual letters and then resizing them to fit the input size of the model. As the model expects individual letters.

The model is a convolutional neural network. It starts with a convolutional layer of 128 filters followed by max pooling, incorporating VGG-like blocks
with repeated convolutional layers and max pooling for feature extraction. It includes dropout layers to reduce overfitting. After flattening the output
from convolutional layers, it has two dense layers with 1000 nodes each for feature interpretation, ending with a 47-node softmax output layer for class
prediction. The network uses stochastic gradient descent for optimization and has 47 possible output classes, one for each letter in the alphabet, each number,
and selected small letters that are different from their capital counterparts (e.g., D and d). The model will then return the predicted letters and return the result as a string.

To run the code, the main.py file must be edited to include the path to the image as an argument to the segmentation method and a .h5 model file as an argument for
test_list_images. The code can then be run using the command `python main.py`.

![src](/images/src.jpg)
*Image 1 showing the given image and letters being identified*

![login](/images/split.jpg)
*Image 2 showing the sentence in black and white and split into letters and words*

The result from image 1 is ['5', '0', 't', 'h', 'I', '5', 'I', '5', 'W', 'I', 'O', 'U', 'e', 'I', 't', 'e', 'S', 't']. Which at first appears completely incorrect, however, it can be seen that 's' is detected as '5' and 'i' is detected as 'I' and 'th' is detected as 'u'. This shows that the issue is not mainly with the model but with how the letters are preprocessed before being given to the model to identify. For example, 'th' is given as one letter instead of two or some letters are missing certain parts (like the dot in 'i').

## What did I learn from this project?
I learned about neural networks and how they can be used to solve real-world problems. I also learned about the importance of data preprocessing. The project was built
using Keras, TensorFlow. I also learned about the importance of hyperparameters tuning and how it can affect the performance of the model.
Some improvements could be to allow the model and image to be given via the command line and improve the image preprocessing.

For further details, the repository is available [here](https://github.com/dalviebenu/AI_Letter_Reader){:target="_blank"}.