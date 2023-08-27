### Neural Netowrks
In supervised learning we model the relation between input and output
variables. In neural network technique, we develop a functional relationship
between input and output variables inspired by the working of the brain.

### Single hidden Units
 a single hidden layer unit is a input (linear combination) assed through a nonlinear function, called an activation function: 
 ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/26e72377-d547-4ca8-9ab2-06d419db9f69)
  
This is the recursive recipe for single layer neural netowkrs.

### Recirsive single layer units
To create recursive recipe of creating single-layer neural network units we need to follow the steps:
• Choose an activation function a(.)
• Compute the linear combination 
• Pass the result through activation and form a(v)

In this example, we take a nonlinear activation function and the parameters 10 and w1. with this we can see the capacity, which is the range of shapes a function can take, given all the settings of its internal parameters:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/98b86dcf-bcdd-4d35-9a44-9a0ccc2cd42f)

### Neural Network Architecture
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/6533fe7e-25b1-4523-955b-da6598f7db32)

in the image above, the grey shapes on the left is a layer. each layer has inputs x1...xn and weights w1...wn. this is the first/input layer. the linear combination of input leads. the sum goes through teh activation function,the blue circle in the diagram. the sum of that, goes through the activation function for each of our layers. therefore n is the number of inputs in each unit
and j is the number of units you have. the output is then fj, on the right of the grey layer. this is a single layer neural network. 
