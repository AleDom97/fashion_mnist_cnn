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
abbiamo due modelli, entrambi di tipo CNN e definiti utilizzando la Sequential API di Keras. They have the following levels in common:

- Layer 1° is a Conv2D layer. In the first model this layes has 64 filters of size 2x2 and a stride of 1, while in the second the size is 3x3. The padding is set to "valid" for the first one and to "same" for the second one. Compared to valid this allows you to make sure the output has the same dimensions as the input which is set to (28, 28, 1), the dimensions of the images in the dataset.
- Layer 2° is a MaxPooling2D layer with a pool size of 2. This reduces the dimensions of the output produced by the previous layer.
- Layer 3° is a Dropout layer with a rate of 30%. This helps prevent overfitting.
- The fourth layer is another Conv2D layer with 32 filters of size 3x3 and a stride of 1. The padding is set to "same".
- The fifth layer is another MaxPooling2D layer with a pool size of 2.
- The sixth layer is another Dropout layer with a rate of 30%.
- The seventh layer is a Flatten layer, which flattens the output from the previous layer into a one-dimensional array.
- The eighth layer is a Dense layer with 256 neurons and a ReLU activation function.
- The ninth layer is another Dropout layer with a rate of 50%.
- The tenth and final layer is a Dense layer with 10 neurons (one for each class) and a softmax activation function.

The model is compiled using the Adam optimizer and the sparse categorical crossentropy loss function.
## **Results**
