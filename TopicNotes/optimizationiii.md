# Optimization III
This is the last optimization section that covers second order optimzation and Newtons method

### Second Order Optimization  
 Second-order derivatives provide information about how the gradient changes with respect to changes in the parameters. They give insight into the curvature and shape of the optimization landscape.
To determine if a single value function g(w) is concave or convex at a given point V, we check the curvature (aka second derivative) info at that point. The function g(w) is convex everywehre if the second derivative is always positive. The matrix g(w) is convex everywhere if ∇^2g(w) is non-negative 
  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/916f36b2-820e-441f-9059-d5b266ca9364)  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/1628d370-bd12-4307-8d95-378ba43bc4f1)  

### Multi input functions - Hessian Matrix
Second order derivatives for multi input functions are in the form of a Hessian Matrix. A stationary point v of a multi input function g(w) is: 
* A local or global minimum if all the eigenvalues of ∇^2g(v) are positive (since it occurs at the convex portion of a function)
* A local or global maximum if all the eigenvalues of ∇^2g(v) are negative (since it occurs at the concave portion of a function
* A saddle point if all the eigenvalues of ∇^2g(v) are of mixed values- some negative and some positive values (since it occurs at the inflection portion of a function)
  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/500ad59a-e834-4f70-b669-1956512eb26d)
   

### Newtons method in Optimization 
Similar to gradient descent, Newtons Method works by using approximations to a function at each step in order to lower its value. However, for Newtons method we use a quadratic approximation, so we can solve the second order Taylor approximation for the stationary point w* by setting its derivative to 0.

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/0a1a0c4d-fd7e-456d-abe9-6b950e65678a)  

If the second derivative is positive, the quadratic approximation is a convex function of t, and its minimum is found by setting its derivative to zero:  
  
  ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/ba32ba01-383b-426d-b070-4c97c2079075)
  
The mininum is:

  ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/b0e6898c-9928-4c66-b308-103e89e6eb33)  

  Newtons iteration is: 

  ![image](https://github.com/erazo-janet/machinelearning/assets/76828004/562c746a-4562-4ab7-b10d-4428450d8c33)  


### Geometric Interpretation of Newtons Method vs Gradient Descent 
In comparison between gradient descent and newtons method in minimizing a function, newtons method uses curvature info to take a more direct rate. Newtons method is a local optima method made by taking steps to stationary points of the 2nd order taylor series approx of a function.
You can see below in the red line  newtons method uses curavture info (second derivative) to take a more direct route, whereas the green line, gradient descent, doesnt: 

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/c427a377-388a-4de6-984e-69a3c401c833)

### Implementation of Newtons Method
For a single input function starting at ppoint w0, Newtons Method creates a sequence of points w1,w2,..... etc that minimizes g by repeately creating the second order taylor series quadratic approx to the function, and travelling to a stationary point of the quadratic. Since Newtons method uses quadratic instead of linear, its more effective than gradient descent since it requires less steps to converge. 




 
