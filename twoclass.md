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

 

 
