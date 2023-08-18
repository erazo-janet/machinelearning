# Optimization I
## Optimization 
When building a machine learning model, optimization is a key step in the training process. We can formalize the search for parameters of a ML model with mathematical functions. These functions are commonly referrred to as **cost functions** which take in a specific set of model parameters and return a score indicating how well we would accomplish a given learning task using that choice of parameters. A high value indicates the paramters would give poor performance, and a low value indicates a better performance. Because a low value corresponds to a high performing model in classification and regression, we always look to *minimize* the **cost function**
Optimization is an important process in data science. We can determine the smallest (or largest) value of a function referred to global minimum (or global maximum). The simplest form of optimization is **Zero-Order Optimization**.
For a simple function taking only one or two values, we can find the minima and maxima by plotting the function over a large range of input values and visualize the minimum or maximum points.
So, its easy to find the optimization of 2 values, but once you get higher in dimension the harder it gets

**Local optima** means that the values are minimal or maximal only locally w/respect to their neighbors and not the function as a whole.  
**Global optima** means the min/max function as a whole. For example:

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/1ce87878-cea9-4632-9cd9-674141cd71de)

### Zero Order Optimization
This is a type of optimization technique used in machine learning and other fields where the function you want to optimize is not directly accessible, and you cannot easily obtain its gradient information. In traditional optimization, having access to the gradient of the objective function is often crucial for efficiently finding the optimal solution.
Mathematicallt speaking, we want to solve a minimzation problem to find a point w* such that   
_g(w*)<=g(w) for all w_   
a function can have multiple global min and global max. Global max can be written as  
_g(w*) >= g(w) for all w_
And local min (and global min)can be written as  
_g(w*)<=g(w) for all w vallues near w*

In summary, its called _Zero Order_ because you dont need to use any information besides the function itself. They dont have access to deritatives so instead of relying on the first oder (gradient) or higher order deritatives, _zero order_ does not need any derivative information. It just needs the function itself.

### Example: Finding the global min of a quadratic function, g(w) =  w^2 + 0.2
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/bf88f55c-26de-42ff-a921-4f8cf4d90063)  
Consider the range [-1,1]    
We can find the mininum by sampling evenly to the left and to the right of 0  
The more samples we take, we can find the global mininum, which in this case is 0. The top 2 graphs show a small amount of sampling. If we stop at only taking 2 samples, we might believe the mininum point is -.5,.5. However, the bottom two graphs show the result of how we can find the actual  global mininum with additional sampling

### Local Optimization
Now that we've discussed global min/max, where we have a large number of input points and the lowest value is the global optima, in Local Optimization we can start from a single point, then work our way down (Sequentially), driving the point towards the approximate mininum point. For example:  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/bb63a2ef-3420-4f12-ad85-5596a6d449c1)  
We start at _w0_, then sequentially refine it (go down the line to the right) and we continue to find another mininum, _w1_, we keep going down the line and we find our local mininum _wk_


### Descent Direction
In the previos example, moving from _w0_ to _w1_ is a move in the direction vector d^0. This is called _descent direction_. So moving from w0 to w1 is equivalent to: w^1 = w^o + d^0  
Then moving from w1 to w2 is equivalent to: w^2 = w^1 + d^1 and so on  to ... w^k = w^(k-1) + d^(k-1)

###Learning Rate
In this optimization process, we need to control the length of the update step, d^k. So, we can have a parameter that scales the length to an appropriate value which is called the _learning rate_, Θ  
Therefore the update step is:  
_w^k = w^(k-1)+Θd^(k-1)_   where Θ > 0  
And the distance traveled at the kth step is:
_|w^k-w^(k-1)| = |(w^k-1) + Θd^(k-1)| = Θd^(k-1)_

### Random selection of Descent Direction
In the previous sections, we had 2 directions to choose from  - positve and negative. But when we have 3 dimensions and higher, its hard to know which direction to go to since theres an infinite amount of directions.  So, we need to figure out what direction to move at point w^(k-1).  
At the k th step, we generate P random directions {d p} where p=1,2,…,P. Each descent direction starts from the prior step w k-1 and leads to the candidate point w k-1 + dp for p=1,2,…,P.   
Once we evaluate those points P, we take the one that gives us the smallest evaluation. If the best point has a smaller eval than the current point, then we move to the new point w^k = d^(k-1) + d^s.  
To summarize: in each step we do a random search, and the random search determines a descent direction by checking a random number of directions. The direction that leads us to a new point with a small value is chosen as the descent direction, and the process is repeated until a point close to a local mininum is found:  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/6d9dd58f-4d39-4369-8922-0b0cc99ea84c)  
You can see above the algorithm is performed by looking at the nmber of steps as a function of the evaluated function at each step. This shows how many steps the function went through until it found its mininum. However, since were just searching a bunch of random directions, computation gets high

### Coordinate Search
This resolves the previous issue, where searching a bunch of directions results in high computation. Coordinate search restricts the set of search directions to the coordinate axes of the input space. In random search, we find a mininum w/respect to ALL parametrers simultaneously. In coordinate search, we minimize a function with respect to ONE coordinate or parameter at a time, keeping everything else fixed:  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/45aa8dfd-e190-4341-9f17-36876bc51614)  
In the image above indicated in green dots, you can see we arent searching random directions. we are searching w respect to one coordinate at a time

