# Perceptron
Classification can be considered as a form of nonlinear regression. Instead of learning this decision boundary as a result of a nonlinear regression, the perceptron derivation determines this decision boundary directly. Perceptron is an algorithm used in supervised learning of binary classifier0. Binary
classifiers indicate if an input consisting of a series of vectors belong to a specific class. It makes its prediction based on a linear predictor function combining a set of weights with the feature vectors.    
Example:  
  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/3e590304-3301-479c-98a7-f7e33e08d2b0)  

In this photo we have two classes of objects. We want to find a line that separates the 2 classes. In Perceptron, we find the best line/hyperplane that seprates the 2 objects together

### Perceptron Cost Function
To recap the cost function, its the difference betweene expected and predicted values. The goal would be to minimize the cost function w/ weights. In logistic regression for two class classification, the data is separated w/each class lyuing on either side. This is a point when the dimension of hte input is N = 1, a line when N = 2 and a hyperplane for any arbitrary N.
The linear decision boundary cuts the input space into two half-spaces, one above the hyperplane and one below. A proper set of weights, w, define a linear decision boundary that separates the two class datasets as well as possible with as many members of one class as possible lying above it, and likewise, as many members as possible lying below it. Our desired set of weights define a hyperplane where as often as possible we have this separation:  
  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/de80c95c-7f68-4dfb-85f1-7d811d403467)  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/3792f4cd-c3f6-4063-a7f4-0bfed8b1f031)  

In the image above, with perceptron we directly learn the decisin boundary to sepaate two classes of data 0 red class +1 and blue class -1. On the right image, we see a dataset with two overlapping classes. Althought he distribution of the data does not allow for complete sepratation, the Perceptron still aims to find a hyperplane that minimzes the number of misclassified points that end up in the wrong half space.

### Minimize the Perceptron Cost
This is often called the Perceptron Cost or the Rectified Linear Unit cost (ReLU). This cost function is always convex (is always positive) and only has a single discontinuous derivative in each input dimension. This implies that we can only use zero or first order optimization technique (and not Newton method). The Perceptron cost always has a solution at w=0 since indeed g(w) = 0. 

### The Softmax Approximation to the Perceptron
Recap: the softmax is defined as: 

 ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/8a8a60ed-9852-4c38-b225-3d3b626a5ecb)  

Which is continuous and has infinite derivaties. The max function of the perception cost is discrete and discontinuous. We use softmax to approximate the max function. We replace the p'th term with its softmax approximation, making the point wise cost and overall cost function as: 

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/2d1b5b86-028d-42c9-967d-9b575e3f8b2d)  
  
Which is the softmax cost derived from the logistic regression on two-class classification. The softmax cost function is a convex function, like the Perceptron cost. However, unlike the Perceptron cost, the Softmax cost has infinitely differentiable. Therefore, Newton’s method can be used to optimize it

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/31942b33-4a0c-4fe9-abfa-477cf5cd881d)  

In the exmaple above, Perceptron g(s) = max (0, s) (green line) compared to smooth softmax approximation g(s) = soft(0,s) = log(1+e^s) (dashed black line). Softmax does not have a trivial solution at zero like Perceptron cost. It shows that softmax closely approximate the Perceptron cost. The difference is how well they are optimized. 

### Regularization
This is the method that avoids the numnber pushing to infinity. We calcualte and optimze the weights and it goes to the softmax/cross entropy cost. We need to stop it. one solution is to choose the local min schemes more carefully by taking fewer steps or halt optimization if the magnitude of the weight grows larger than a large predefined constant. Another approach is to contorl the magnitude of the weights during the optimization. These procedures are called regularization. The linrar decision bounary is:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/83894a4e-582f-489d-835a-744c07dc5673)  

### Distance from the decision boundary

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/7fee96df-10f3-45cc-9424-655e557114c7)  

Imagine we have point xp above the linear decision boundary on a translate of the decision boundary where b+ xtw = Beta > 0 (the same argument holds if the point is below the decision boundary). To compute the distance of point xp from the decision boundary, we find the location of its vertical projection as x’p. We now
want to find the signed distance between xp and its vertical projection- the length of the vector x'p - xp times the sign of Beta  which here is +1 since we assume the point to be above the decision boundary


