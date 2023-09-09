# fashion_mnist_cnn
Basic classification: Classify images of clothing.
This is a project done at the university where the Fashion-MNIST clothing classification problem is solved.
## **Prerequisites**
This project is run with the following libraries installed:

- Tensorflow
- Keras
- Numpy
- Matplotlib
- Sklearn
  
You can test it on a platform for running code on the Cloud like Google Colab
## **Dataset**
The dataset composed of 70,000 small square grayscale 28x28 pixel images of items from 10 types of clothing, which are associated with integers from 0 to 9 representing the class labels.

## **Models Architecture**
We have two models, both of the CNN type and defined using the Keras Sequential API. They have the following levels in common:

- 1° Layer is a Conv2D layer. In the first model this layes has 64 filters of size 2x2 and a stride of 1, while in the second the size is 3x3. The padding is set to "valid" for the first one and to "same" for the second one. Compared to valid this allows you to make sure the output has the same dimensions as the input which is set to (28, 28, 1), the dimensions of the images in the dataset.
- 2° Layer is a MaxPooling2D layer with a pool size of 2, same for both models. The size of the output produced by the previous layer is thus reduced.
- 3° Layer is a Dropout layer with a rate of 30% which helps prevent overfitting and is the same for both models.
- The 3 previous levels form a block that is repeated once more, in this case 32 filters are used in the Conv2D level.
- 7° layer is a Flatten layer, which flattens the output from the previous layer into a one-dimensional array.
- 8° layer is a Dense layer with 256 neurons and a ReLU activation function.
- 9° layer is a Dropout layer with a rate of 50%.
- 10° layer is a Dense layer with 10 neurons and a softmax activation function. we have a neuron for each class.

The model is compiled using the Adam optimizer for improving the accuracyt and speed of models and the sparse categorical crossentropy loss function.
