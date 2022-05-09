# Deep Learning
## Lesson 8

## Introduction to CPU and GPU 

- CPU (central processing unit) is a generalized processor that is designed to carry out a wide variety of tasks.A CPU (central processing unit) and a GPU (graphics processing unit) work together to boost data throughput and the number of simultaneous calculations
within an application. 

<p align="center">
  <br>
  <img src="https://user-images.githubusercontent.com/45029614/165884838-2e768e9d-9e98-481a-9a5c-d2f07d0900cb.PNG" width="550" title="CNN">
</p>

- GPU (graphics processing unit) is a specialized processing unit with enhanced mathematical computation capability, ideal for computer graphics and machine-learning tasks.

<p align="center">
  <br>
  <img src="https://user-images.githubusercontent.com/45029614/165885556-aec3494b-1348-4ab5-bae8-e63478427e77.PNG" width="550" title="CNN">
</p>

- GPUs were created to create visuals for computer graphics and  video gaming consoles, but from the early 2010s, they have also been used to speed up calculations involving large amounts of data.

- For example,at any given time, a graphically intense video game may have hundreds or thousands of polygons on the screen, each having its own movement, color, lighting, and other characteristics. That kind of workload is too much for a CPU to handle. Graphic processing units (GPUs) are used to solve this problem.

<p align="center">
  <br>
  <img src="https://user-images.githubusercontent.com/45029614/165884891-5273e8a7-daee-4bef-b47c-3b08d617110a.PNG" width="550" title="CNN">
</p>


<p align="center">
  <br>
  <img src="https://user-images.githubusercontent.com/45029614/165885794-f6259d83-4543-4703-81bd-153d25ebd66c.PNG" width="850" title="CNN">
</p>

## NVIDIA VS AMD 

NVIDIA and AMD rae two of the most popular companies who manufacture GPUs. In deep learning, we mostly used the NVIDIA GPUs.Over the years,
Nvidia has been putting hardware-level optimizations to better support AI-related tasks. Besides, their CUDA software development kit (SDK) 
supports all major machine learning frameworks. Combined with a large, helpful community and libraries, Nvidia is the perfect suit for most ML enthusiasts.

<p align="center">
  <br>
  <img src="https://user-images.githubusercontent.com/45029614/165885391-6748b48c-60a8-4b20-a9b6-3c4b506871bd.jpg" width="375" title="CNN">
</p>

## Deep Learning Softwares

This section of the lesson delas with the common libraries used for the application of deep learning. Some of the common libraries/framework used in deep learning include Tensorflow, Pytorch and Caffe2. The point of deep learning frameworks include

* Easily build big computational graphs
* Easily compute gradients in computational graphs
* Run it all efficiently on GPU

If we try to compute compute complex calculations in Numpy ourselves, it becomes inefficient once the network becomes complicated. Also, Numpy is CPU based so it doesn't run on GPU and we can't take advantage of parallel processing. Using the frameworks such as Tensorflow, we can just write a single piece of code and the framework calculates complex calculation like gradient calculations for you. Also, you can tell frameworks to run calculations on either CPU or GPU yourself.


<p align="center">
  <img src="https://user-images.githubusercontent.com/45029614/166175660-6d99352b-4b66-4b43-ba65-13a74e75cbf0.PNG" width="650" title="CNN">
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/45029614/166176317-cd87cdbf-f65e-4772-8bd7-edb1529bf5b2.PNG" width="650" title="CNN">
</p>

<strong>Tensorflow</strong><br>
The Google Brain team created TensorFlow for internal Google use in research and production. In 2015, the first version was released under the Apache License 2.0. In September 2019, Google launched TensorFlow 2.0, an improved version of TensorFlow.

<p align="center">
  <img src="https://user-images.githubusercontent.com/45029614/166176466-17fa44d8-c5a2-416d-aa8b-ae643633dc7c.jpg" width="350" title="CNN">
</p>
<strong>Pytorch</strong><br>
PyTorch is an open source machine learning framework based on the Torch library, largely created by Facebook's AI Research division for applications such as computer vision and natural language processing.<br>

<p align="center">
  <img src="https://user-images.githubusercontent.com/45029614/166176589-258c1d63-df03-434b-9a74-cedd7558ce8a.jpeg" width="350" title="CNN">
</p>

<strong>Caffe2</strong><br>
The deep learning framework Caffe (Convolutional Architecture for Fast Feature Embedding) was created at the University of California, Berkeley. With its unrivaled performance and well-tested C++ codebase, the original Caffe framework was ideal for large-scale product use cases.

<p align="center">
  <img src="https://user-images.githubusercontent.com/45029614/166176616-e7330afc-d4ce-4911-b31e-bb8c4f9ed695.png" width="350" title="CNN">
</p>
