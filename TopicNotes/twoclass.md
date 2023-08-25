# Linear Two Class Classification
This is a supervised learning problem. In two-class classification the output of a dataset takes on only two discrete values or two classes. For example, object detection is such a process- you even detect an object or do not. Diagnostic of medical images is another kind of such process- either there is a malady or it is not.
The classification is different from regression where we have a continuous dataset. In regression, data comes in the form of P input/output pairs xp,yp  with each input xp is an N-dimensional vector. In classification, the corresponding output yp is no longer continuous but takes two discrete values. In the context of classification, the yp value the output takes is called _labels_ and all points sharing the same labels are called _class_0 of data

### Logistic Regression
This is a classification problem where the output can only take two values, like 0 &1 for example. It often gives poor fits. even introducing a step function does not provide a perfect fit to the data. Instead of tuning the parameters of a linear model and then passing the results to a step function, we can tune the parameters of a linear model after passing it through a step function.

### Cost Function
We want the point (xp,yp) to lie on the correct side of the decision boundary - aka the output yp to lie on the proper step. To find weights that satisfy the set of P equalities we form a least squares cost function by squaring the difference betweeen both sides of each equality and taking their average:  

 ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/b615fbfa-ce86-4346-be3c-94cd8f69e3f1)    
 It is not possible to minimize this least squared cost function using local minimization since at every point the function is flat locally. The gradient descent and Newton methods are not effective here because the derivative of a flat function, needed in these methods, are zero.  
 To minimize the least squares cost function,we can replace the step function with a continuous approximation that matches it closely called the _Logistic Sigmoid Function_  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/a0e3c985-6492-4f58-bb73-69da56a231c6)  

Here, you can see sigmoids function on the left. On the right, you can see it corresponding to different weight. By increasing the weight w, you can get close to the step function:  

 ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/5b1609ce-45cd-4d78-842f-12c7b3005a4d)  
  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/de34cbed-2f75-471d-ab14-daac6cef376c)  

Fitting a logistic sigmoid to classification data by minimizing the cost function is called performing logistic regression. While the resulting cost function is uaully nonconvex, it can be properly minimized using a host of local optimization techniques.  

### Logistic regression using the cross entropy cost 
So we have a distribution of points around 0 or 1. Bu theres some probability tha a point will belong to 0 group or class 1 group. So how do we find that probability? This is where the _cross entropy cost function_ comes into play. Its assigning the probability of a point to belong to one class or another. Since the value only belongs to 0 or 1, we need an optimzed cost function to resolve the function, called the _point wise cost, aka log error_, defined as:  

 ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/c1199fc1-e044-4d57-886d-3e32bc1fdc67)  

This point wise cost is always positive with a mininum at point 0. Since the output can only take two values, we can write the overall cost function (the average of the point wise cost over all P data points) as:  

 ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/3ece70ce-1cc3-4d00-8684-04bc4813ab1a)  

 This is Cross Entropy cost for logistic regression. 
  
### What is Cross Entropy?
Cross Entropy is the measure between two probability distribtions for a given random variable or a set of events. One is the trye probabilty, and the other is the probabilty in which the object has. In _information theory_,one quantifies the number of bits required to encode and transmit an event.  
  
  _Low probability event (suprising): More Information_  
  _High probability event (not suprising): Less Information_  

_Information_, h(x), can be calculated for an event x, given the probablity of the event P(x) as: h(x) = -log(P(x))  

_Entropy_ is the number of bits required to transmit a randomly selected event from a probability distribution:  

 _Skewed probability distribution (less supurise): Low entropy_
 _Balanced probability distribution (more suprise): High entropy_  

 _Entropy_, H(x), can be calculated for a random variable with a set of x in X discrete states and their probabilities P(x) as: H(X) = -sum x in X P(X) * logP(X)  (this is the information * the probability of the event happening = total probability summed over all the points gives us the entropy)

The cross entropy loss is defined as:  

 ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/725f20ec-b446-4df9-b3d8-f0d5bb4bc691)  
  
Where ti and si are the ground truth and the score (prediction) for each class i in C respectively. In a binary classification where C=2, the cross entropy loss is defined as:  

 ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/f064d117-51a7-449f-a0ad-8328ee61e3a2) 
   
Where it is assumed that there are two classes C=1 and C=2. t1 and s1 are the ground truth and the score (probability) for C1. t2 = 1 – t1 and s2 = 1 – s1 are the ground truth and score for C2. Here we divide a multi-label classification problem into C binary classification.
   
Summary: Cross entropy builds upon the entropy from information theory and calcualtes the number of bits required to represent or transmit an average event from one distribution compared to another. In machine learning, cross entropy is used primarily for evaluating and training models, especially in binary and multi-class classification tasks. 

### Minimizing the Cross Entropy Cost 
We minimize cross entropy in machine learning for a fundamental reason: it serves as a measure of the dissimilarity or "error" between the predicted probabilities and the true probabilities (or labels) of the data. By minimizing this error, we aim to make the model's predictions as close as possible to the ground truth  
  
Since CE is always convex, we can use the gradient and 2nd order netwons method  using simple derivative rules:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/612d1529-96d4-498b-a63f-f30a965bba40)  

 we could also use the hessian cross entropy function as:  

  ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/c1af1a38-f5c1-4ef9-9e7c-2b43d40cff7e)  

### Logistic Regression and the Softmax Cost
This is similar to logistic cost function, but in least cost functio the output has to be between 0 and 1. In softmax, its -1 to 1. Similar to cross entropy too, but instead of our data sitting in a step function, it uses a sign function since it returns the numerical sign of its input:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/e2568d72-c87d-44eb-8f71-b1600f73a80e)  

 We could then use a linear model through the sign function w a liner decision boundary defined by all points x where xtw = 0. Any input sitting on the deicision bounary can be assigned a label at random. A point is classified crorectly when its true label is predicted, when sign (ctpw)-yp. Else its misclassified 

 ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/8ae38989-fdad-4526-8bfb-0444eb5e8bd8)  

Similar to the sigmoid function, we can form a least squares cost function for recovering optimal model weights using tanh(.) function  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/c53e6c22-2b28-4d34-8cdd-e241fc0abbe8)  

This function is non-convex, with flat regions, requiring specialized local methods for proper minimization. Our final softmax function is:  

 ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/cc1b5bb2-2edb-4e74-8ba3-23f2ec4fda62)  

This cross entropy cost function is always convex regardless of the dataset. Also, the Softmax and Cross Entropy Cost functions are equivalent (upon changing yp =-1 to yp=0)






   


 

 
