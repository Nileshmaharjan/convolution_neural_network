## Visualizing activation of deep learning models

## Activations

## Nearest Neighbours

Any model architecture can be visualized with the filters of any layer. Only the initial layers are comprehensible using the technique. The last layer is useful for the nearest neighbor approach. The ImageNet dataset, when arranged with nearest neighbors, looks as follows;:

![image](https://user-images.githubusercontent.com/41963640/170696849-e64b4f22-9e23-49e9-ba58-0cae295d853a.png)

- Looking at this image, you can see that the same objects appear together. One of the interesting things is that the animals such as the dog, monkey, and cheetah appear together though they are not trained under one label. Nearest neighbour visualization of the images is useful when objects are similar.
- Pixels between the images are different.
- Feature space between images must be similar.


## Dimensionality Reduction

Dimensionality reduction refers to techniques that reduce the number of input variables in a dataset.

More input features often make a predictive modeling task more challenging to model, more generally referred to as the curse of dimensionality.

## Maximally activating patches

- Pick a unit and then run many images through the network 
- Visualize patches that produce the highest output values.
- One simple way to get a hint of the features that neurons learn is by measuring their responses to test images. We feed many images to the network, and then for a particular neuron of interest, we extract patches of those images which maximally activated it. 

Reference link https://ml4a.github.io/ml4a/visualizing_convnets/


## Occlusion Experiments

- Occlusion experiments are performed to determine which patches of the image contribute maximally to the output of a neural network.
- The occlusion experiments tell us that our convolution neural network is actually learning some meaning patterns like detecting the face of a dog from the input. That means that the model is truly picking up the location of a dog instead of identifying based on the surrounding context like a sofa or a couch.
-
Reference link https://towardsdatascience.com/visualizing-convolution-neural-networks-using-pytorch-3dfa8443e74e


## Gradients

## Saliency maps

- Saliency maps are a visualization technique to gain better insights into the decision-making of a neural network. They also help in knowing what each layer of a convolutional layer focuses on. This helps us understand the decision making process a bit more clearly.
- Saliency maps help us visualize where the convolutional neural network is focusing in particular while making a prediction. Suppose that we feed the above image of the cat to the model. And the model correctly predicts it as a cat.

Reference Link: 
https://debuggercafe.com/saliency-maps-in-convolutional-neural-networks/

## Guided Backpropagation
- Neurons act like detectors of a particular image features.
- Interested in what image features that the neuron detects, doesn't care about what it doesn't detect.
- Like DeconvNets, in Guided Backpropagation we only backpropagate positive error signals – i.e. we set the negative gradients to zero (ref). This is the application of the ReLU to the error signal itself during the backward pass.


## Gradient ascent
- Gradient ascent works in the same manner as gradient descent, with one difference. The task it fulfills isn’t minimization, but rather maximization of some function.
- Generate a synthetic image that maximally activates the neuron.
- Updating the pixels of the image which causes the neuron to be maximally activated.
- Has a regularizer which forces the generated image to look natural.


## Deep Dream
- DeepDream is an experiment that visualizes the patterns learned by a neural network. Similar to when a child watches clouds and tries to interpret random shapes, DeepDream over-interprets and enhances the patterns it sees in an image.
- It does so by forwarding an image through the network, then calculating the gradient of the image with respect to the activations of a particular layer. The image is then modified to increase these activations, enhancing the patterns seen by the network, and resulting in a dream-like image. T
- Reference Link: https://www.tensorflow.org/tutorials/generative/deepdream

## Feature Inversion
- Take an image send it through the network.
- Record the feature value for one of the images.
- Reconstruct image based on feature representation.

## Texture synthesis
- A texture synthesis method starts from a sample image and attempts to produce a texture with a  visual appearance similar to that sample.
Reference Link: http://graphics.cs.cmu.edu/nsp/course/15-462/Fall04/assts/assignment4.html

## Gram Matrix

- Consider two vectors(more specifically 2 flattened feature vectors from a convolutional feature map of depth C) representing features of the input space, and their dot product give us the information about the relation between them. The lesser the product the more different the learned features are and greater the product, the more correlated the features are. In other words, the lesser the product, the lesser the two features co-occur and the greater it is, the more they occur together. This in a sense gives information about an image’s style(texture) and zero information about its spatial structure, since we already flatten the feature and perform dot product on top of it.
- Now take all C feature vectors(flattened) from a convolutional feature map of depth C and compute the dot product with every one of them(including with a feature vector itself). The result is the Gram Matrix(of size CxC).

Reference Link: https://towardsdatascience.com/neural-networks-intuitions-2-dot-product-gram-matrix-and-neural-style-transfer-5d39653e7916


## Neural style transfer
- Neural style transfer is an optimization technique used to take two images—a content image and a style reference image (such as an artwork by a famous painter)—and blend them together so the output image looks like the content image, but “painted” in the style of the style reference image.
- This is implemented by optimizing the output image to match the content statistics of the content image and the style statistics of the style reference image. These statistics are extracted from the images using a convolutional network.

Reference Link: https://www.tensorflow.org/tutorials/generative/style_transfer




