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
* its cheaper in computational costs
  
We can take steps for minimization by defining the general form wk = w k-1 + α d k and the negative gradient direction dk = -∇g(w k-1). Such a sequence of steps takes the form:  
_w k = w k-1 – a ∇g(wk-1)_  
Taking these steps will take us close to the local minimum point of the function g. The extra term in this equation (∇g(wk-1) is the gradient descent algorithm.  
Heres an example for a single input function:   
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/11ce6008-3db2-45a2-9682-e5012162c6cc) 
At each step, we take the first order taylor series approx. to the function (red lines) and take the descent direction of this tangent line as our descent direction for the algorithm. So with our function here g(w), we start our first approx. at w0 and do the taylor series approx. then we move in that negative gradient descent direction to get to w1, then so on and so fourt  
So, in summary, we want to find the downward direction (aka steepest descent direction) on this function g, travel a short distance along this direction, hop back on to the function g, then repeat until slope = 0

### Choice of step length for gradient descent
When youre choosing a step length (aka learning rate) for gradient descent, we have to keep 2 things in mind:  
* use a fixed value for each step of a gradient descent, taking the form 10 y where y is often negative integer
* Use a diminishing step length a = 1/k at the k’th step of the run

Example: Quadratic function g(w) = w^2  
  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/4ef19f2e-e703-4e57-ae8b-e4f74bea3786)  

The first top left graph shows our starting step length, and we dont reach 0 cus we took really small steps. Then we increase our step lengths on the second graph to find our minimum point 0, then the third graph on the top, the steps become too large. Here are some criteria we can follow to figure out when to STOP the gradient descent:  
* 1. If the gradient descent wk = wk-1 – a ∇g(wk-1) does not move from the prior point w k-1 - i.e. (∇�(� !"# ) ≈ 0.
* 2. When steps no longer make much progress- i.e. when 1/N ||wk – wk-1 || is smaller than some � value.
* 3. When corresponding evaluation no longer differ substantially 1/N |g(wk ) – g (wk-1)| is smaller than some � value.
* 4. Run the algorithm for a fixed number of iterations.

Although there are a few advantages to gradient descent, there are some disadvantages:  
* The negative gradient consists of a direction and magnitude, like any vector. Any of these two could cause problem.
* The direction of gradient descent can rapidly oscillate during a run of gradient descent, producing zig-zag steps, taking a considerable time to converge to a minimum point.
* The magnitude of the gradient descent can vanish rapidly near the stationary points, causing the gradient descent to slowly crawl near minima and saddle points.

### Crawling of Gradient Descent
When we start our descent, we someitimes go from large steps to small steps. The steps get smaller when you get close to the min, where the movement from one point to the next will be slow, because the distance travelled at each step near the stationary point is not always completely known by the step length value, a.  
Therefore, the length of a general gradient descent step is equal to the value of the step length parameter, a, times the magnitude of the descent direction. This slow behavior is called _crawling_.  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/e7352476-4784-4977-a48a-314fb9d82fa9)  

You can see here the first gradient is a big step, then slowly crawls when it reaches near the mininum point. This is bc the magnitude of the gradient is large away from the min point and vanishes closer to it







