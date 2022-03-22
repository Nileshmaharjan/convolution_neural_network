## Loss function

## Definition
- Tells how good our current classifier is.
- It's a method of evaluating how well our algorithm models our dataset.
- If predictions are totally off, loss functions output a higher number.
- Bascially, tell algorithm what types of errors you care about and what sort of errors to trade off against
- If they're pretty good, outputs to a lower number.

  ![total](https://user-images.githubusercontent.com/41963640/159428099-c8df09a4-e777-450a-90ea-a2bbd21c9286.PNG)

## Multiclass SVM loss
- Inspired by Support Vector Machines, which uses scoring function f to map out data points to numerical scores for each class labels.

 ![svm_loss](https://user-images.githubusercontent.com/41963640/159428479-64093a73-f7cf-4e4d-ad14-26343dc9b163.PNG)
	
## Hinge Loss
- The points that are farther away from the decision margins have a greater loss value, thus penalising those points.

![hinge_loss](https://user-images.githubusercontent.com/41963640/159429156-5fd5b383-a808-40b9-9353-1a4670ea151e.PNG)

## Calculating Multiclass SVM loss

![multiclass_svm_loss](https://user-images.githubusercontent.com/41963640/159429338-471d0406-9b33-4851-a5b9-29d409e79ab4.PNG)

## Questions Multiclass SVM loss

-  What if the cars score are changed?
	- If the scores of the car is jiggled a little bit, the svm loss is retained as it only cares about the correct score being one more than the incorrect scores, the margin of one is retained.
-  Find maximum and minimum loss
	- Minimum loss of zero, Maximum loss of infinity (correct score is very very negative, look at Hinge loss plot)
-  At intialization W is small so all s tends to 0, what is the loss?
	- (No of classes - 1)
-  What if sum was all over classes?
	- The loss increases by 1
-  What if mean was used instead of sum?
	- The loss doesn't change as mean just rescales the data sets
- ![q6](https://user-images.githubusercontent.com/41963640/159431680-255d4d2e-dc9c-4717-a987-db658512c047.PNG)
	- Computes different loss function

## Regularization
In mathematics, computer science, particularly in machine learning and inverse problems, regularization is the process of adding information in order to solve an ill-posed problem or to prevent overfitting. 
 ![regularization](https://user-images.githubusercontent.com/41963640/159432301-f9629db1-4908-4d2c-a777-99657f5164ae.PNG)

## L1 vs L2 Regularization

- A regression model that uses L1 regularization technique is called Lasso Regression and model which uses L2 is called Ridge Regression.
- The key difference between these two is the penalty term.
- Ridge regression adds “squared magnitude” of coefficient as penalty term to the loss function. Here the highlighted part represents L2 regularization element.
- Lasso Regression (Least Absolute Shrinkage and Selection Operator) adds “absolute value of magnitude” of coefficient as penalty term to the loss function.
- The key difference between these techniques is that Lasso shrinks the less important feature’s coefficient to zero thus, removing some feature altogether. So, this works well for feature selection in case we have a huge number of features.


## Softmax Classifier (Multinomial Logistic Regression)

- The Softmax classifier uses the cross-entropy loss. The Softmax classifier gets its name from the softmax function, which is used to squash the raw class scores into normalized positive values that sum to one, so that the cross-entropy loss can be applied.
	![softmax_classifier](https://user-images.githubusercontent.com/41963640/159433573-8b0fe1bc-760e-4b50-924f-f71cf8c99fe6.PNG)
	![softmax_classifier_2](https://user-images.githubusercontent.com/41963640/159433662-84651f3e-8544-440f-8e07-8a45649d79f4.PNG)

## Questions Softmax Classifier

- What is the min/max possible loss ?
	- Theoretical minimum loss: 0
	- Theoertical Maximum loss: infinity

- What if W is small so all scores is 0 ?
	- log(C) (Log of total classes)

## Difference between Softmax and SVM
	- Softmax classifier provides probabilties for each class, SVM doesn't.
	- SVM gets the datapoint over the bar and correctly classifiy or not.
	- Softmax tries to imporve every single data point to get better and better.
	

## How do we select the W? Optimization

- Follow the slope
- In 1 dimension the derivative of a function 
	![derivative](https://user-images.githubusercontent.com/41963640/159437982-6eea74cb-c0e1-4732-b97d-2452894cffd0.PNG)
- In multiple dimension, gradient	(The steepness of the slope at that point is given by the magnitude of the gradient vector)
- Slope in any direction is the dot product of direction with the gradient.
- Direction of steepest descent is negative gradient.

## Gradient Descent and Stochastic Gradient Descent

- An iterative first order optimization algorithm used to find a local maximum/minimum of a given function.
- While in GD, you have to run through ALL the samples in your training set to do a single update for a parameter in a particular iteration, in SGD, on the other hand, you use ONLY ONE or SUBSET of training sample from your training set to do the update for a parameter in a particular iteration.
- Thus, if the number of training samples are large, in fact very large, then using gradient descent may take too long because in every iteration when you are updating the values of the parameters, you are running through the complete training set. On the other hand, using SGD will be faster because you use only one training sample and it starts improving itself right away from the first sample.
- D often converges much faster compared to GD but the error function is not as well minimized as in the case of GD. Often in most cases, the close approximation that you get in SGD for the parameter values are enough because they reach the optimal values and keep oscillating there.















