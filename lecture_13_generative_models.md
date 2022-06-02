## Supervised Vs Unsupervised Learning

![image](https://user-images.githubusercontent.com/41963640/171550192-224d0bc5-d372-4152-aa19-7a16ae587c0f.png)



## Generative Models

A Generative Model is a powerful way of learning any kind of data distribution using unsupervised learning and it has achieved tremendous success in just few years. All types of generative models aim at learning the true data distribution of the training set so as to generate new data points with some variations. But it is not always possible to learn the exact distribution of our data either implicitly or explicitly and so we try to model a distribution which is as similar as possible to the true data distribution. For this, we can leverage the power of neural networks to learn a function which can approximate the model distribution to the true distribution.

## PixelRNN

- PixelRNNs are generative neural networks that sequentially predicts the pixels in an image along the two spatial dimensions


## PixelCNN

- A PixelCNN is a generative model that uses autoregressive connections to model images pixel by pixel, decomposing the joint image distribution as a product of conditionals. PixelCNNs are much faster to train than PixelRNNs because convolutions are inherently easier to parallelize; given the vast number of pixels present in large image datasets this is an important advantage.


Reference Link: https://towardsdatascience.com/auto-regressive-generative-models-pixelrnn-pixelcnn-32d192911173#:~:text=PixelCNN%20lowers%20the%20training%20time,performance%20is%20worse%20than%20PixelRNN.


## VAE (Variational Autoencoder)

- VAE is one of the most popular approach to learn the complicated data distribution such as images using neural networks in an unsupervised fashion. 
- The model aims to learn the underlying probability distribution of the training data so that it could easily sample new data from that learned distribution. 
- The idea is to learn a low-dimensional latent representation of the training data called latent variables (variables which are not directly observed but are rather inferred through a mathematical model) which we assume to have generated our actual training data.

Reference Link: https://towardsdatascience.com/deep-generative-models-25ab2821afd3

## Generative Adversarial Network

- GANs are neural networks that learn to generate realistic samples of the data that trained them.
- For instance, for a given photo of handwritten digits, GANs learn how to generate realistic photos of more handwritten digits.

![image](https://user-images.githubusercontent.com/41963640/171549135-757967aa-bdd8-4eef-9759-c105e6a34fc7.png)


GANs consist of two interlinked networks

- The generator 

Data distribution is useful as it allows us to generate similar images from the distribution.

The generator takes a random distribution (also known as 'noise' in GANs literature) as input and learns a mapping function that maps the input to the desired output, which is the actual underlying distribution of the data.


The discriminator

The discriminator's role is to judge and assess the quality of the generator's output images. The discriminator is a binary classifier in theory. It takes images as input and returns a probability that the image is real.

![image](https://user-images.githubusercontent.com/41963640/171549151-8089ab0a-f552-4271-8b46-072d59c7da7e.png)


Reference Link: https://towardsdatascience.com/fundamentals-of-generative-adversarial-networks-b7ca8c34f0bc


