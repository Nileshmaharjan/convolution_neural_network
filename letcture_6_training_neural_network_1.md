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



Leaky ReLU
f(x) = max (0.01x,x)

- Does not saturate
- Computationally efficient
- Converges much faster than sigmoid/tanh in practice 
- will not die 

Parametric Rectifier (PReLU)

f(x) = max(alpha * x, x)


Exponential Linear Units (ELU)

- All benefits of ReLU
- Closer to zero mean outputs 
- Negative saturation regime compared with Leaky ReLU adds some robustness to noise 





