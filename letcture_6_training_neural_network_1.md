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


Maxout Neuron

- Generalizes ReLU and Leaky ReLU
- Linear Regime! Does not saturate ! Does not die 



TLDR: In practice 

- Use ReLU. Be careful with your learning rates
- Try out Leaky ReLU / Maxout / ELU
- Try out tanh but don’t expect much
- Don’t use sigmoid


# Data Preprocessing 

Step 1 : Preprocess the data
  - zero-cenetered the data (for images we just do zero mean)
  - normalized data 


TLDR: In practice for Images: center only
- Subtract the mean image (e.g. AlexNet)
(mean image = [32,32,3] array)
- Subtract per-channel mean (e.g. VGGNet)
(mean along each channel = 3 numbers)



# Weight Initialization 

Q: what happens when W=0 init is used?
A: All neurons will do the same thing, gets updated the same way. But, we want every neuron to learn different things

- First idea: Small random numbers
(gaussian with zero mean and 1e-2 standard deviation)

## picture 










