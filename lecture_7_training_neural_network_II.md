## Background
What happens when loss changes quickly in one direction and slowly in another direction

There is very little progress in the gradient descent in the shallow direction and jitter along the steep direction.

 <p align="center">
  <br>
  <img src="https://user-images.githubusercontent.com/45029614/163305143-711a74d0-e38f-4612-9718-edd569154cf4.PNG" width="750" title="CNN">
</p>

## Disadvantages of SGD

* <h3>Noisy Derivatives</h3>
  We don’t compute the precise derivate of loss function in Stochastic Gradient Descent, instead, we’re estimate it on a small batch. So, we’re not always going in the
  optimal direction, because our derivatives are ‘noisy’.
* <h3>Local Minima Problem</h3>
  The gradient descent gets stuck.In the picture below, the first loss curve has a local minima and the gradient descent gets stuck at that dip.

<p align="center">
  <br>
  <img src="https://user-images.githubusercontent.com/45029614/163306003-e86424f5-87e5-42db-99c2-d20a82c62820.PNG" width="450" title="CNN">
</p>

* <h3>Saddle Point Problem</h3>

  In mathematics, a **saddle point** or minimax point is a point on the surface of the graph of a function where the slopes (derivatives) 
  in orthogonal directions are all zero (a critical point), but which is not a local extremum of the function. Hence, the gradient gets stuck at the saddle point.
  Saddle points are very common in the higher dimension compared to the local minima.

<p align="center">
  <br>
  <img src="https://user-images.githubusercontent.com/45029614/163306547-08155d92-1f9d-4db8-89df-30361e0ca57d.PNG" width="350" title="CNN">
</p>

## Optimizers
 Optimizers help to reduce the loss function by changing the weights and the learning rate attributes. SGD, Adagrad,RMSProp,Adadelta,Adam etc are types of optimizers found in deep learning.

## Types of Optimizers

- SGD with Momentum

By adding a momentum term in the gradient descent, gradients accumulated from past iterations will push
the cost further to move around a saddle point even when the current gradient is negligible or zero. This removes the saddle problem.
Also, adding exponentially weighed averages can provide a better estimate closer to the actual derivate than the noisy calculations.

<p align="center">
  <br>
  <img src="https://user-images.githubusercontent.com/45029614/163311157-45cead0a-6ffa-4c78-aacd-da0a192ac03e.PNG" width="850" title="CNN">
</p>

- AdaGrad Optimizer

The learning rate is different for each weight parameter in the AdaGrad Optimizer. The frequency of the parameter determines the learning rate i.e higher the frequency of occurence, lower is the learning rate and vice versa.It divides the learning rate by the sum of squares of all previous gradients of the parameter.

When the network gets larger and larger, there is insignificant change in the new learning rates, and the new weight parameter is almost similar to the old weight parameter and the neural network is unable to learn any further. AdaDelta and RMSProp solve this problem.

<p align="center">
  <br>
  <img src="https://user-images.githubusercontent.com/45029614/163983658-e110352d-d2e7-4a15-9318-e546fc078a86.PNG" width="450" title="CNN">
</p>

- RMSProp

Root Mean Square Prop (RMSProp) works by keeping an exponentially weighted average of the squares of past gradients. RMSProp then divides the learning rate by this average to speed up convergence.

- Adam Optimizer
Adaptive Moment Estimation (Adam) combines ideas from both RMSProp and Momentum. The adaptive moment adaptation optimization is a stochastic gradient descent approach that uses adaptive first-order and second-order moment estimation.

## Reducing Gap between Training and Test Error

In machine learning, we care about the gap between the test and train error and minimize the gap to know how our model performs on unseen data. One of the easy way to do this is by the Model Ensemble process.

<p align="center">
  <br>
  <img src="https://user-images.githubusercontent.com/45029614/163990654-150edce1-fafe-4745-89e6-da9c1e4119ee.PNG" width="650" title="CNN">
</p>

-Model Ensemble

Ensemble approaches combine many learning algorithms to achieve higher predictive performance than any of the individual learning algorithms could.

## Regularization
Regularization is often used to improve the performance of a machine learning model. This technique forces us not to learn a more complex or flexible model, to avoid the problem of overfitting. Regularization techniques used for neural networks are gifven below.

- Dropout
Dropout technique drops out a fraction of the input layer randomly to minimize complexity and prevent overfitting during each forward pass. Dropout prevents the neural network to be heavily dependent on only one feature.

<p align="center">
  <br>
  <img src="https://user-images.githubusercontent.com/45029614/163995413-547e10c9-0967-4916-8e0b-036b6b9ee25d.PNG" width="650" title="CNN">
</p>

- Data Augmentation
Data augmentation refers to the modification or augmentation of a training dataset. The data augmentation process increases the diversity of data significantly. Common ways to augment the image data in CNN are by chnaging the brightness, rotating the image, adding noise to the image etc.

<p align="center">
  <br>
  <img src="https://user-images.githubusercontent.com/45029614/163997487-b661f962-720d-4f32-86c4-884be4748504.PNG" width="650" title="CNN">
</p>

- Fractional MaxPooling
Fractional max pooling is slightly different than regular max pooling. In regular max pooling, you downsize an input set by taking the maximum value of smaller N x N subsections of the set (often 2x2), and try to reduce the set by a factor of N, where N is an integer. Fractional max pooling, as you might expect from the word "fractional", means that the overall reduction ratio N does not have to be an integer. The sizes of the pooling regions are generated randomly but are fairly uniform.
