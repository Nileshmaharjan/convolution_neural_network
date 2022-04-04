## Convolution Neural Network

A convolutional neural network (CNN) is a type of artificial neural network used in image recognition and processing that is specifically designed to process pixel data.
These networks are widely used in 
- Image recognition and Image classification
- Object detection
- Recognition of faces, etc.


## Why prefer CNN over ANN for image data?

1. Feedforward neural networks can learn a single feature representation of the image but in the case of complex images, ANN will fail to give better predictions, this is because it cannot learn pixel dependencies present in the images.

2. CNN can learn multiple layers of feature representations of an image by applying filters, or transformations

3. CNN considers the context information in the small neighborhood and due to this feature, these are very important to achieve a better prediction in data like images. Since digital images are a bunch of pixels with high values, it makes sense to use CNN to analyze them. CNN decreases their values, which is better for the training phase with less computational power and less information loss.


## Different layers of CNN
1. Input Layer: The input layer in CNN should contain image data. Image data is represented by a three-dimensional matrix. We have to reshape the image into a single column.
2.  Convolution layer:  This layer is used which creates several smaller picture windows to go over the data.
3.  ReLU Layer: This layer introduces the non-linearity to the network and converts all the negative pixels to zero.
4.  Pooling Layer: Pooling is a down-sampling operation that reduces the dimensionality of the feature map. 
5.  Fully Connected Layer: This layer identifies and classifies the objects in the image.
6.  Softmax / Logistic Layer: The softmax or Logistic layer is the last layer of CNN. It resides at the end of the FC layer. Logistic is used for binary classification problem statement and softmax is for multi-classification problem statement.
7.  Output Layer: This layer contains the label in the form of a one-hot encoded vector.


## Why use ReLU Activation function?
- RELU is a non-linear activation function. This operation is applied to each pixel and replaces all the negative pixel values in the feature map with zero.
- This layer helps in the detection of features, decreasing the non-linearity of the image, converting negative pixels to zero which also allows detecting the variations of features.

## Why do we use pooling layer in CNN ?
-  pooling layers to reduce the size of the input image so that it speeds up the computation of the network.
-  It reduces the dimensionality of each feature map by retaining the most important information.

## Size of the feature map
- If our input image has a size of n x n and filters size f x f and p is the Padding amount and s is the Stride, then the dimension of the feature map is given by:

Dimension = floor[ ((n-f+2p)/s)+1] x floor[ ((n-f+2p)/s)+1]




































































