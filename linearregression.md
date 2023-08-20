# Linear Regression
With Linear Regression, we aim to fit a line (or hyperplane) to a set of input/output data points.Regression can be used in machine learning to drive home a particular point about the data under study, visually study a correlation, learn about a model to make percise predictions, and more. Least squares and Least Absolute Deviations are among these techniques.

### Least Squares Linear Regression
Least squares involve fitting a line or a hyperplane in higher dimensions to a set of input/output data points. Each dimension of the input is referred to as a feature or input feature in machine learning. the parameters w1,w2,....wn are feature weights:  
  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/caef18e6-248d-4d18-83f9-d7dfd555f85d)  

  Example of datasets fited by a line in 2d (left) and with a hyperplane in 3d (right):  
    
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/e2a7e989-a16b-494b-b0c6-9ece46c1f04e)  

Where w0 is the bais and w1 is the slope.  

### The lease squares cost function
Here, the goal is to find the best parameters of the hyperplane that fit the data. The cost function measures how well a model with a particular choice of parameters fits the data. For a given set of parameters in the vector W, the cost function computes the total squared error between the hyperplane and the data. the best fitting hyperplane is the ones whose parameters minimize the error. We want xp^t to be as close as possible to the output or the error which is the difference between xtp - yp to be as small as possible  

### Minimization of the cost function
If the least squared cost function si large, the error will be large, and the poorer the fit will be. We want the optimum parameter vector w that minimizes g(w). If the function is convex, we can use newtons step to minimize it. We can also use gradient descent until reaching the minimum of the function


### Least absolute deviation
Sometimes with the cost functions is that if there are large errors, it can overestimate the error. Then when you minimize the cost function, it tries to minimize the large errors. This happens when there are outliers in the data. For example, here, we dont get a good fit because of the outlier:  
  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/2d101687-6975-45ed-9b97-7afd3bb0dff6)  

 Instead of looking at the squared error we can look at the absolute error for each approximation:  
  
 ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/647dc6a6-9d80-47b9-a6db-1a088303d7bc)  

This funciton is always convex, since its secondderivativee is always 0, so we can use only zero and first order methods to optimize it 

Heres an example of least squares and least absolute deviation cost function. We run gradient descent for both with the same number of steps. The least squares is in black and the least absolution is in purple. You can see the cost function for least absolute is way smaller than the one of least squares which means least absolute is a better method and provides a better fit 

 ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/3ba73f61-a6ee-4e7c-b492-723c2471890f)  

### Weighted Regression
Sometimes we want to emphasis or deemphasis the imporance of some features when calculating regression models. This is called weghted regression. Sometimes tehre could be duplicate data points and we want to see what happens to the cost function. If we assume B versions of the input/output pairs (xp,yp) then we have:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/65935376-aa25-4a39-90a9-6893c7808227)  

example: making predictions using a trained model:  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/7b4eb0e6-1f84-46b8-8b84-0f6f1cd198e4)  

Adjusting the weights: adjusting the weights of a single datapoint affects the final model in a weighed linear regession.  As the weight is increased, the regression line becomes more focued on the red data point. If we increase the weight enough, the regression line fits the red point:  
  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/6bde3bda-7ac3-436f-b17d-8d2705bc0a4f)  

### Multi Output Regression  
So up until now weve talked about how linear regression conssits of inputs and outputs with the form xp,yp. Its possible that both the input and output are vectors, and this is called multi output regression. Our cost function becomes:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/72ca2bbe-b985-4904-aac4-1b6ec5adfaf7)  

  


  
 
  

  
