# Activation Functions

Sigmoid function 
- Squashes numbers to range [0,1]

Problem
- Saturated neuron may kill of the gradient
- Sigmoid outputs not zero centered
- exponential function is a bit compute expensive 


Tanh function 
- Squashes numbers to range [-1.1]
- zero centered


Problem
- Still kills the gradient 


ReLU (Rectified Linear Unit)

- Computes f(x) = max(0,x)
- Does not saturate in the positive region
- Computationally efficient
- Converges much faster than sigmoid/tanh in practice 

Problem

- Not zero centered
- Saturation in the negative region





