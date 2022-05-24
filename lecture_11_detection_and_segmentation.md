## Semantic Segmenation

Semantic image segmentation is the task of classifying each pixel in an image from a predefined set of classes. In the following example, different entities are classified.

![image](https://user-images.githubusercontent.com/41963640/170036985-72b7aed1-649b-4f3d-bee6-1137e7d639bb.png)
![image](https://user-images.githubusercontent.com/41963640/170037001-f3e6afa5-cd94-4144-8cf4-058133c797c1.png)



## Upsampling Techniques

The Downsampling network is intuitive and well known to all of us but very little is discussed about the various techniques used for Upsampling.

The most widely used techniques for upsampling in Encoder-Decoder Networks are:

1. Nearest Neighbors: 

In Nearest Neighbors, as the name suggests we take an input pixel value and copy it to the K-Nearest Neighbors where K depends on the expected output.

![image](https://user-images.githubusercontent.com/41963640/170036242-cdc48f41-3e05-4689-bb9b-169fcc38f105.png)


2. Bi-Linear Interpolation: 
In Bi-Linear Interpolation, we take the 4 nearest pixel value of the input pixel and perform a weighted average based on the distance of the four nearest cells smoothing the output.
![image](https://user-images.githubusercontent.com/41963640/170036321-b73f1f99-4664-4de9-87e7-18cf2e865b6d.png)


3. Bed Of Nails: 

In Bed of Nails, we copy the value of the input pixel at the corresponding position in the output image and filling zeros in the remaining positions.
![image](https://user-images.githubusercontent.com/41963640/170036358-845d6ffb-ac0f-45e2-aeb1-f580571456f0.png)


4. Max-Unpooling: 
The Max-Pooling layer in CNN takes the maximum among all the values in the kernel. To perform max-unpooling, first, the index of the maximum value is saved for every max-pooling layer during the encoding step. The saved index is then used during the Decoding step where the input pixel is mapped to the saved index, filling zeros everywhere else.
![image](https://user-images.githubusercontent.com/41963640/170036393-b6f6a254-ec15-442b-9b59-47126bcf9565.png)



All the above-mentioned techniques are predefined and do not depend on data, which makes them task-specific. They do not learn from data and hence are not a generalized technique.


Transposed Convolutions

Transposed Convolutions are used to upsample the input feature map to a desired output feature map using some learnable parameters.
The basic operation that goes in a transposed convolution is explained below:
1. Consider a 2x2 encoded feature map which needs to be upsampled to a 3x3 feature map.

![image](https://user-images.githubusercontent.com/41963640/170036439-0c960e24-8025-4b3a-b3d9-a307c99a005d.png)


![image](https://user-images.githubusercontent.com/41963640/170036455-5980b14a-9405-4d4e-9ef8-579648517dd0.png)

2. We take a kernel of size 2x2 with unit stride and zero padding.

![image](https://user-images.githubusercontent.com/41963640/170036482-d6d85e0d-3d70-4c4b-9865-95098c3ada7f.png)
Kernel of size 2x2

3. Now we take the upper left element of the input feature map and multiply it with every element of the kernel as shown in figure 10.

![image](https://user-images.githubusercontent.com/41963640/170036515-c962234c-87c8-4a41-894e-9f396f6d4d75.png)

4. Similarly, we do it for all the remaining elements of the input feature maps
![image](https://user-images.githubusercontent.com/41963640/170036570-fc69e806-bd8e-4389-9f0b-1c9f3e947ecc.png)


5. As you can see, some of the elements of the resulting upsampled feature maps are over-lapping. To solve this issue, we simply add the elements of the over-lapping positions.
![image](https://user-images.githubusercontent.com/41963640/170036591-7aa2da46-1dd7-494e-bd89-39172aa2e9aa.png)

6. The resulting output will be the final upsampled feature map having the required spatial dimensions of 3x3.


## Image/Object localization 
It is a regression problem where the output is x and y coordinates around the object of interest to draw bounding boxes.

Input: an image

Output: “x”, “y”, height, and width numbers around an object of interest

![image](https://user-images.githubusercontent.com/41963640/170037676-af027a5b-4ff9-4a97-98af-4a0108461b5b.png)

Locate the presence of objects in an image and indicate their location with a bounding box.

Input: An image with one or more objects, such as a photograph.
Output: One or more bounding boxes (e.g. defined by a point, width, and height).


## Object detection 

It is a complex problem that combines the concepts of image localization and classification. Given an image, an object detection algorithm would return bounding boxes around all objects of interest and assign a class to them.

Input: an image

Output: “x”, “y”, height, and width numbers around all object of interest along with class(es)

![image](https://user-images.githubusercontent.com/41963640/170037782-56e8c916-fba5-4452-8ac4-438edcfabc4d.png)




## R-CNN, or Region-based Convolutional Neural Network, consisted of 3 simple steps:

- Scan the input image for possible objects using an algorithm called Selective Search, generating ~2000 region proposals
- Run a convolutional neural net (CNN) on top of each of these region proposals
- Take the output of each CNN and feed it into a) an SVM to classify the region and b) a linear regressor to tighten the bounding box of the object, if such an object exists.

These 3 steps are illustrated in the image below:
![image](https://user-images.githubusercontent.com/41963640/170037977-bc847bff-2782-4835-b164-0200072c499f.png)


In other words, we first propose regions, then extract features, and then classify those regions based on their features. In essence, we have turned object detection into an image classification problem. R-CNN was very intuitive, but very slow.

## Fast R-CNN

R-CNN’s immediate descendant was Fast-R-CNN. Fast R-CNN resembled the original in many ways, but improved on its detection speed through two main augmentations:

- Performing feature extraction over the image before proposing regions, thus only running one CNN over the entire image instead of 2000 CNN’s over 2000 overlapping regions
- Replacing the SVM with a softmax layer, thus extending the neural network for predictions instead of creating a new model

![image](https://user-images.githubusercontent.com/41963640/170038131-f828cfbb-5827-404a-bf87-e6f1969ab609.png)
As we can see from the image, we are now generating region proposals based on the last feature map of the network, not from the original image itself. As a result, we can train just one CNN for the entire image.

In addition, instead of training many different SVM’s to classify each object class, there is a single softmax layer that outputs the class probabilities directly. Now we only have one neural net to train, as opposed to one neural net and many SVM’s.

Fast R-CNN performed much better in terms of speed. There was just one big bottleneck remaining: the selective search algorithm for generating region proposals.


## Faster R-CNN

Once we have our region proposals, we feed them straight into what is essentially a Fast R-CNN. We add a pooling layer, some fully-connected layers, and finally a softmax classification layer and bounding box regressor. In a sense, Faster R-CNN = RPN + Fast R-CNN.

![image](https://user-images.githubusercontent.com/41963640/170038563-cbd86b6c-ca4d-46f6-8a0a-6508c5e21457.png)


## Instance Segmentation

In this blog, the focus will be on using the instance segmentation in the RedAI application.

Instance segmentation is a computer vision task for detecting and localizing an object in an image. Instance segmentation is a natural sequence of semantic segmentation, and it is also one of the biggest challenges compared to other segmentation techniques. 
The goal of instance segmentation is to get a view of objects of the same class divided into different instances

![image](https://user-images.githubusercontent.com/41963640/170039113-bfc170db-8791-4532-b4d4-d4567764a492.png)

So, unlike in semantic segmentation, all three dogs have different colors, or labels. Semantic segmentation does not recognize more of the same objects in one image as different, while instance segmentation does. For example, if there are multiple dogs in one image, the instance segmentation will recognize it.


Mask R-CNN

Mask R-CNN model to solve the instance segmentation problem. That’s a deep neural network based on a faster R-CNN architecture that, in addition to classification and detection, also provides mask prediction for each bounding box.

![image](https://user-images.githubusercontent.com/41963640/170039222-64119f97-5a48-49af-9fc7-9b72b6be5849.png)






