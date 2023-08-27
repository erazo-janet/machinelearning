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
we can create a compact version of two layer network where each vector is the weight of each unit stacked together into a matrix:  
A![image](https://github.com/erazo-janet/machinelearning/assets/76828004/e580d8a1-562e-42f8-b4f9-eee1850611f9)  
  
where each column of the unit corresponds to each unit. 

### Two layer and general multi hidden layers
the full two layer nerural network model is:  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/6da624bd-8213-441b-a060-44bac2e512db)  

To summarize, here are the steps to take for recurvie relatino for multi layer units:  
* Choose an activation function a(.)
• Construct Ul-1 number of layer units 
• Compute the linear combination 
• Pass the result through activation and form a(v)


 ### Summary:
 ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/6a3979a4-480e-45f4-b931-aee9c6c99b11)  
 each of these outputs from the input layer goes into each unit in the next layer l so its fully connected. finally we sum it up with the final weight producing the final result for the unit. summing up the output of the neural network represented in the hollow circle

 we can see here there is 1 input layer, many hidden layers, and finally an output. so thats why its called recursive cus it repeats itself:  

  ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/14cb7182-756b-4a2e-954e-6fafbfb64045)  

### Selectig the right network architecture
how do we select the number of layers and units? the best way is to test. the more layers we have the more expensive it is in terms of computtion. increasing number of units wont change the activation much, but layers can

### Biological Neural Nets 
The human brain contains about 10^11 neurons which work together to perform cognitive tasks. for example, we use about 10^5 neurons to look at something. These are the biological components of a nueron:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/84b76dfe-0c58-49d9-b7aa-a8de79b640ea)  

The human brain consists of neurons or nerve cells which transmit and
process the information received from our senses. Many such nerve cells
are arranged together in our brain to form a network of nerves. These
nerves pass electrical impulses i.e the excitation from one neuron to the
other.
The dendrites receive the impulse from the terminal button or synapse of
an adjoining neuron. Dendrites carry the impulse to the nucleus of the
nerve cell which is also called as soma. Here , the electrical impulse is
processed and then passed on to the axon. The axon is longer branch
among the dendrites which carries the impulse from the soma to the
synapse. The synapse then passes the impulse to dendrites of the second
neuron. Thus, a complex network of neurons is created in the human brain.  
Neurons are inactive until the net input to the cell body aka soma reaches a certain threshold, where the neuron gets activated and fires a electro chemical singal, hence the name activation funciton.  

 ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/7c99c4ab-d4db-44f0-bf6e-f54850540c7b)  

 now we can map this mathematically:    
   
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/b9305bab-42cd-45b0-bdd4-0dee45b4ddac)
  
 ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/5e737747-859d-490d-a17b-2fd185d451a8)  

 here on the left we have 1,x1...x6 which are the dendrites aka inputs, then the blue points are we get to SOMA, where we sum them up at each point. so each of these sum up to a synapse, which is where we cna meet our threshold. in mathematical terms its an activation function which produces an electrical singal that goes to the next neuron which goes to the next layer. 

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/7223c63a-4f2a-4c09-8ef1-16c129d72044)  

above we can see our inputs x0..xn and our weights w0..wn and XW is our inputs. these get summed up into soma and then run through an activation term, which is when the singals activate the neuron. it travels through the axom to the nect neuron through synapses which is essentially the next layer.  

now we can look at this through a non linear classification network. we can choose a network with 4 hidden layers and 1 input with 10 inputs.we choose the parameters of this by minimzing the softmax function via gradient  
  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/e2e93073-c3e3-439a-b282-1a7061e4727f)  

 Random autoencoder:  
if we have two nonlinear functions, encoeder fe and decoder df, we can tune the parameters of the autocoders. in this example we have 9 instances of the function, each called a manifold, wehre both fd and fe are five hidden neural networks with 10 units in each layer. 
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/26d6b248-64e3-418a-a9e2-2b3cf974d65d)  

### Activation Functions
the choice of the activation function is important to optimize a model. the step and sigmoid activation function, neurons act like a swich either being off 0 or on 1. However, this kind of step function can lead to a flat cost function making it hard to optimize sowe cna use logistic sigmoid, it can lead to a vanishing gradient problem.  
rectified linear unit (ReLU) activation: only maps the negative input values to zero, so networks using this activation function dont have that vanishing gradient problem. when using this, you have to pay attention when initalizing and training a network for the nonpositive inputs

To summarize:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/41f8479b-8426-4e86-bdeb-17f87e5f93ff)  

we have the inputs going through the dendrites, the weighted sum goes through the soma in the nucleus and then hte output from that goes to an activation function which identifies if the neuron is going to be activated. the output then goes into the next neuron  

the most widly used activation functions are:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/5386e7b4-592a-4cb0-b88a-036925eebe4f)  

### Training and Interference  
  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/a6e5a6d0-ad2f-44f4-a2cc-55b784cd4446)  

Training is when a deep learning algorithm is applied on data with known output.
The weights in a deep learning structure are optimized so that the error between
the input and output features is minimized. Using the trained model to predict output
of unknown features is called “inference”. We optimize the weight and the parameters in the function, we train it in a system with no outputs. So if we want to identify a car, bicycle , a cat, we take a sample and train the network to identify the object. once we train, we apply it to the sample that does not know the output, so we apply the network thats trained to it. 

Overview of deep learning training:  

 ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/46494353-e692-4d12-a178-8e1d01516298)  
  
 ### Backpropagation
 Its not efficient to test the relation for all possible parameter variations. so once we have deep layers we have a ton of parameters to validate which is not practicalto optimize all parameters and weights so we can backpropagate which uses the error contribution of each neuron after data is processed. So the training set compares the output. the difference between the input and output gives us the error, so we need to reduce the error. the backpropagation is when we take that error, go back and change all the parameters so it reduces the error. this is an approach to compute gradients via computer program effective for multi layer neural networks. How it works:  
* Backpropagation dynamically calculates the gradient (derivative) of the loss function with respect to weights in a network to find the minimum (optimize the function)
* It optimizes the performance of the network by adjusting the
weights (in gradient descent algorithm)
* Error and gradient are calculated for each node.
* Intermediate errors are transmitted backwards through the
network (backpropagation)
* The aim is to optimize the weight so that the neural network
can learn how correctly map arbitrary inputs to outputs 

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/f4b56591-c68f-47fc-b74b-b45ed21e0ee8)  

 * Inputs (X) arrive through the connected path
• Input is modeled using weights (W) that are selected randomly
• The output for each neuron from the previous layer is calculated to the output layer
• Error in the output is calculated- error = actual output – real output
• Loop back from the output layer to the hidden layer to adjust the weights and decrease
• The error
• Repeat the process until the desired output is achieved.

if the error is large, we go back to the previous layer and adjust the weights to decrease the error 

### Deep Learning Training

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/ab97a939-5c57-431f-82f0-d42d8051f6a7)

 Here in deep learning we have multiple layers. we have a training sample of a face, bike and strawberry. we want to train the model to identify these so we know what output we will get. if a face is identifed as a bike, thatts an error so we go back and fix it. then we go to interference where we have the final weights and model to have the correct output  

 ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/d7646839-ba25-4abc-a847-00ca949375e4)  

 






