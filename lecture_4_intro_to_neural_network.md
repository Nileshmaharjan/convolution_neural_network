## Backpropagation Algorithm
- Why backpropagation algorithm? Neural nets will be very large; impractical to write down gradient formula.
- Backpropagation algorithm is probably the most fundamental building block in a neural network.
- The algorithm is used to effectively train a neural network through a method called chain rule. In simple terms, after each forward pass through a network, backpropagation performs a backward pass while adjusting the model’s parameters (weights and biases).
![backpropagation](https://user-images.githubusercontent.com/41963640/160386191-6301f40b-0967-4dd1-a033-52cfaa4be08f.PNG)
![bp2](https://user-images.githubusercontent.com/41963640/160386438-ca9e126a-4c82-414d-8dc1-788b96c476dd.PNG)

## How backpropagation algorithm works 
![bp3](https://user-images.githubusercontent.com/41963640/160386622-f44187ca-7227-46dc-ab4b-332ae78e6c2c.PNG)

## Sigmoid function
- The sigmoid function is a special form of the logistic function and is usually denoted by σ(x) or sig(x). 
-  It is given by:
    - σ(x) = 1/(1+exp(-x))
    - The values lie between (0 to 1)
    - The derivatives value lie between (0 to .25)
- The sigmoid function is used as an activation function in neural networks.When the activation function for a neuron is a sigmoid function it is a guarantee that the output of this unit will always be between 0 and 1. Also, as the sigmoid is a non-linear function, the output of this unit would be a non-linear function of the weighted sum of inputs. Such a neuron that employs a sigmoid function as an activation function is termed as a sigmoid unit.
![bp4](https://user-images.githubusercontent.com/41963640/160387263-957815e5-6df9-438a-a621-fb54f1c1d7d9.PNG)

## Vanishing gradient problem
- Te derivative of the sigmoid function ranges between 0 to 0.25. As the number of layers increase, the value obtained after multiplying derivates(using chain rule) is very very small, thus not helping in changing the weights as the old weight and the new weight are approximately similar or equal.



## Patterns in backward flow

- Add gates acts as a gradient distributor.
- Max gate acts as a gradient router. (only one will get the full value of the upstream gradient)
- Mulitply gate acts a a gradient switcher. (the value of the gradient is calculated by local gradient of another input * upstream gradient)
![bp5](https://user-images.githubusercontent.com/41963640/160387797-f7277648-8f99-4467-a421-393f879f3750.PNG)


## Jacobian Matrix

- In machine learning, the Jacobian matrix aggregates the partial derivatives that are necessary for backpropagation; the determinant is useful in the process of changing between variables.
![jm1](https://user-images.githubusercontent.com/41963640/160388228-0d7a0aec-0717-46ee-a673-474aa0c8bc62.PNG)
![jm2](https://user-images.githubusercontent.com/41963640/160388519-f801e342-8de1-4311-9664-b8f72e173ef3.PNG)


## Forward and backward pass

Forward
- The "forward pass" refers to calculation process, values of the output layers from the inputs data. It's traversing through all neurons from first to last layer.
- compute result of an operation and save any intermediates needed for gradient computation in memory

Backward
- "Backward pass" refers to process of counting changes in weights (de facto learning), using gradient descent algorithm (or similar). Computation is made from last layer, backward to the first layer.
- apply the chain rule to compute the gradient of the loss function with respect to the inputs


## Inspiration for Neural Network

![nn](https://user-images.githubusercontent.com/41963640/160391865-d1d7c29d-9e60-4999-b8b2-1ea3cc997dc8.PNG)
![nn2](https://user-images.githubusercontent.com/41963640/160391918-52ac3bd3-ac73-4abe-beda-2d721f34668b.PNG)


## Activation function
- Function that you use to get the output of node. It is also known as Transfer Function.
![af](https://user-images.githubusercontent.com/41963640/160392216-b6ff29a3-4426-46cf-9466-b1a90c897545.PNG)


## ReLU
- Operates with max(0,z) 
- Solves vanishing gradient problem 
- Dead neurons for values which are negative.

## Neural networks: Architectures
![nn3](https://user-images.githubusercontent.com/41963640/160392330-b13ea0ca-73eb-4ed9-aa27-e68f7be155b6.PNG)


















