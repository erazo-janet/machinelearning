# Optimization II

This section covers additional optimization topics such as First order, hyperplanes, Steepest Ascent, Gradient Descent and Convergence Criteria

### First order derivatives: mininum of a function  
To find the mininum of a function, you have to find the slope of the tangent line to the function at any given point. The mininum is where the tangent line/hyperplane is completely flat, aka slope = 0  
With this, In calculus, the dervative of a single point function at a point gives us info on the slope. a local minimum or maximum of a function occurs where the first derivative (gradient) is zero. If the second derivative is positive, it's a local minimum; if it's negative, it's a local maximum.   
For N=1, any point in the function _g(w)_  where dg(v)/dw = 0 is a mininum 
for multi input functions, any N Dimensional point V where the partial derivatives of g(wn) = 0  is a mininum:  
  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/e304668d-4031-4a78-a329-fc24c42f24b8)    
  
This is called the first order system of equations    
   
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/d31515b9-0c85-4c66-9076-3620f8c158b0)  
  
You can see in the image above, this shows the points where the derivatives of teh function equals zero which means the line/hyperplane tangent to the function has a slope = 0. The left graph is an example of single input and the right graph is an example of a multi-input quadratic function  
Another example below, showing the functions of g(w) then its derivative, showing that the slope = 0:  
  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/649aec06-fefb-4a3d-8685-c8d63dfb55df)  

### Hyperplanes
A hyperplane is a geometric concept that extends the idea of a plane from two-dimensional space to higher-dimensional spaces. In two dimensions, a plane is a flat, two-dimensional surface that extends infinitely in all directions. In three dimensions, a plane is still a flat surface, but it extends infinitely in the three-dimensional space.
It can be characterized as: _h(w1, w2, …, wN) = a + b1 w1 + b2 w2 + … + bN wN_ Where a1, b1 through bN are scalar parameters. This can be written in vector form as: h(w) = a + bT w where bT and w are vectors. When N=1, we have the equation of a line: _h(w) = a + b w_

### Steepest Ascent and Descent Directions
For a one dimensional hyperplane the input space is also one dimension, so for any point w^0 in the input space, there are only 2 directions it can go - right or left - aka positive or negative. If our dimension N >1, theres infinite directions to move to. So how do we find the direction of the steepest descent or ascent?  
To find the direction for the steepest ascent at a point w^0, we need to find the unit direction _d_ so that the value of h(w0+d) is maximum   
For example:  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/0f049b1e-08ad-4781-8ea5-a5d9e0afa2a2)   
In the image above, if we start from w0 and move to the right, _h_ increases. this is an ascent direction.  
if we move to the left, it decreases the value of _h_. This is a descent direction. Therefore there are 2 directions on a line when N = 1  
  
But if we are in higher dimensions, N>1, theres an infinate amount of directions to go. Some directions give us descent, some give us ascent. So how do we find the direction that gives us the LARGEST ascent and descent?


### Gradient Descent
This is a popular optimization algorithm in machine learning. The goal is to find the values of the parameters that minimize a given objective function. It's particularly useful for training machine learning models because it enables the model to learn from data by adjusting its parameters to fit the data as closely as possible.  
Its popular because:  
* the negative gradient direction provides a descent direction for the function locallly
* its easier to calculate the gradient of ta function than search for a large number of random directions
  
We can take steps for minimization by defining the general form wk = w k-1 + α d k and the negative gradient direction dk = -∇g(w k-1). Such a sequence of steps takes the form:  
_w k = w k-1 – a ∇g(wk-1)_  
Taking these steps will take us close to the local minimum point of the function g. The extra term in this equation (∇g(wk-1) is the gradient descent algorithm.  
Heres an example:  










