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

## picture 

- First idea: Small random numbers
(gaussian with zero mean and 1e-2 standard deviation)
- Weights should not be same, or else all neurons will do same thing.

Strategy 1 

- Weights are basically distributed using Uniform distribution (-1/√fin , 1/√fin )

Strategy 2
Xavier Normal
- Weights are distributed using W should be between N(0=mean, σ=SD) (N= Normal distribution)
- σ = √(2/fan_in + fan_out)

Xavier Uniform 
-  Weights are basically distributed using Uniform distribution (-√6/√(fin + fout) , √6/√(fin + fout) )

Stragey 3
- He init(ReLu)
He Unifrom 
- Weights are basically distributed using Uniform distribution (-√6/√(fin) , √6/√(fin) )

He Normal
- Weights are distribtued using normal distribution)
-  σ = √(2/fan_in)


# Xavier Initialization (start with this but breaks when using ReLU, can be tackled though!)
## picture

# Papers on Weight Initialization 

Proper initialization is an active area of research…
Understanding the difficulty of training deep feedforward neural networks
by Glorot and Bengio, 2010
Exact solutions to the nonlinear dynamics of learning in deep linear neural networks by
Saxe et al, 2013
Random walk initialization for training very deep feedforward networks by Sussillo and
Abbott, 2014
Delving deep into rectifiers: Surpassing human-level performance on ImageNet
classification by He et al., 2015
Data-dependent Initializations of Convolutional Neural Networks by Krähenbühl et al., 2015
All you need is a good init, Mishkin and Matas, 2015


# Batch Normalization 
- To make each dimension unit gaussain , apply :

## picture

- Usually inserted after Fully Connected or Convolutional Layers and befoe nonlinearity

## picture 

What it does?

- Improves gradient flow through the network
- Allows higher learning rates
- Reduces the strong dependence on initialization
- Acts as a form of regularization in a funny way, and slightly reduces the need for dropout, maybe










