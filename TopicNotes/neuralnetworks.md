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
Since threre could be alot of hidden layers in a neural netowrk, we can represent each layer in a compact way by a matrix.  
x1...xn are input vectors. the weights, for each unit we have 1 vector for w. but we have u1, the number of untis. when we stack it together we havea  matrix:
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/ac1975e3-1bb9-4d70-9ef5-4b8584865b50)  

the activation function can also be expressed as a vector so we can represent the model (hollow circke) as:  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/c230a525-a623-495e-bc69-2b6a4345ef4a)  

### Two hidden layer units
here, we have input functions and weighted values, but now all the inputs go into a second, hidden layer. therefore the output of the first ones f1 now goes into the second layer, f2:   
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/a55fbc25-9338-4011-91f1-f8e68759b5ea)  

 This recursive nature can be seen in a recursive recipe as:
• Choose an activation function a(.)
• Construct U1 single-layer units 
• Compute the linear combination 
• Pass the results through activation and form a(v)
    
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/aa0663c2-8aea-4808-b4c4-bae2ff8cf2f9)  

 this is referred to as fully connected. every dimension of the input is connected to every unit in the first hidden layer, and each unit in the first hidden layer is connected to every unit of the second hidden layer. at the right, we can seea linear combination of the u2 two layer units produces the final layer of the network

### Compact representation of two layer networks

 

