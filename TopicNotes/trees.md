 # Tree based learners 

  Stumps are the simplest of a tree based learner, which is a simple step function f(x) which has 3 turnable parameters: two step levels and a split point parameter. You can see the stump tree on the left:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/bd2f038e-21a2-4fb1-bd3c-49fd949177dd) 

by putting many stumps together we get a tree on the right. we can go into different trees by having another split point, the images located on the bottom half of the image. we have 3 splitting points and 4 values, which are to be optimzed. S is the root of the tree, then we have the leaves of the trees. therefore the leaves are the horizontal red lines. the dotted lines are the splitting ponits. 
once the tree becomes deeper and deeper, we have higher capacity. 

### Creating deep trees via recursion
Using recursing, we can construct deeper trees by applying the same concept
used to build a stump to each of its leaves- by splitting each leaf in two. This
recursion tree is a tree of depth two, with three split points and four distinct
leaves. A depth two tree has significant more capacity than a stump, since the
location of the split points and the leaf values can be set in a multitude of
different ways. This recursive idea can be applied to any leaf of a depth-two
tree, to create a depth-three tree and so on. Deeper a tree is, more capacity it
contains with each unit being able to take on a wider variety of different
shapes.  
We can show that a tree of general depth D will have 2^d − 1 split
points and 2^d leaves. This has 2^d − 1 tunable parameters. This procedure is
called growing of a tree  
Unlike fixed-shape and neural network universal approximators, tree-based
units are defined locally. This means that when we adjust one parameter of a
polynomial or a neural network unit, it can globally affect the shape of the
function over the entire input space. However, when we split any leaf of a
tree, we are only affecting the shape of the tree locally at that leaf. 


### Regression Trees
Consider a set of points like the ones in the first panel below, with splitting points shown as lines. we want to use the stumps to do a regression on the data points. there are 2 main parameters here, the splitting points and the leaves, which are the horizontal ones.
if you take the hostontal lines which are the leaves, we can shift the split points. therefore we can shift them to the right   
  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/b43bc40b-ec21-4cf1-9c48-881134c3f281) 

Top-left: A nonlinear regression dataset. Top-right: three stumps with fixed leaf values
whose split points can vary. Middle: each stump instance is slid horizontally to the input
data panel by varying its split point value, creating three corresponding stair-case like least
squares costs. Bottom: Each cost in the middle panel is constant between consecutive
inputs implying that we only need to test one split point per flat region e.g the mid-point. 

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/b0c7e823-0474-4f4d-a70a-5b5708a23d0e)  

in the image above, we have our data points and split point (dotted line). On the right you can see we have our leaves (vertial lines) whhere we fit the leaves to the data points. These 2 vertical leaves are identified as:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/4d4bcb86-b8cf-4ffe-ba0d-ad2ffe05141d)  


### Step-by-Step optimization of regression stumps
To tune all three parameters (leaves and split points) of the stump for the purpose of
regression, we need to take the following steps:
• Create a set of candidate split point values by recording every mid-point between
our input data along each of its input directions (the left image above)
• For each candidate split point we determine the stump’s leaf values optimally,
setting them to the mean of the training data output to the left and right of the
split point (we take the min of the values)
• Compute its least squares cost value
• After doing this for all candidate split points, we find the best stump with optimal
split point and leaf values as one that provides the lowest cost value.
For a dataset of P points, each of input dimension N, there are a total of N(P-1_
split points to choose from over the entire input space

example:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/78008f8c-ecc0-4e32-b995-30dbd7699ca5)

From the top left, we find the split line first which is the mid between the first and second points which is the dotted blue line. Our stump is the one point we have. Then we find hte least square solution for all the points. we find the deviation of those points from the line which gives us the cost function. Then we shift to the second split point on the second and third graph. We find the least square solition and cost function ont he second row. Then we go to the next points, and the mean from all the points to the left and right determine the position of the leaf. to chosoe which one of these options are optimal, we look at the cost function on the bottom row.   

### Deeper Regerssion Trees
Sometimes when growing a tree there are moments where we shouldnt split a leaf, sometimes the split doesnt covey any more useful information. When the value of the leaf does not change by splitting it, we should stop splitting it. example of different depths:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/0bff0dc0-f862-48db-98ee-5a5a4ee428d0)  

do we need to go that deep though? consider the cost, and if it gives you any new results.

## Classification Trees
There are 2 ways to classify a tree: find the optimal split point where leaf values are fixed. our leaves are horizontal/flat, however if we determine optimal leaf values when split points are fixed, we can optimze the leaf values.  we can split the point between -1,+1 to classisify the dataset and use the softmaxx funciton to find the optimal values. 


![image](https://github.com/erazo-janet/machinelearning/assets/76828004/d86a7a32-3f21-4d3b-aedb-e4755be5fa61)  

we have a set of points here we want to classify. the top points are -1,+1. there are 9 points, and on the right we show the split points for each of them. we find the leaf values based on the standard mode. taking min isnt helpful, so mode, the number of repeated points is helpful. we have 8 points here so the mode is 2 so we go for the higher mode. so in classification we take the mode, and in regession we take the mean. this is called the majority vote. sometimes theres an imbalance where the numbers in one class are higher than the other. in this case the stumps will be identical, and we choose the leaf value based on the balanced mode. we do this by counting the number of points belonging to each class in the leaf and determine the mode by picking the class associated with the largest count. For a multi-class dataset with C classes, the weighted count for the �#$class on one
leaf can be written as:   

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/ef7cca7f-e4c0-4c2c-b38e-9d53f21a6374)   

 ### Random Forest
 One often does not use a single recursively defined regression or classification tree,
but a bagged ensemble of them. Bagging involved combining different crossvalidated models to produce a simple higher performing model. This can be done
with recursively defined trees employing the cross validation techniques. Each tree
can be trained on a random portion of the training data taken from the original
dataset and grown to a predetermined maximum depth and afterwards, bagged
together. While the bagging can be done with any universal approximator, it is
especially useful for tree-based learners. The overfitting problem is less significant
for tree-based learners than other approximators. Tree-based learners do not often
lead to oscillatory behavior as the growth of each tree can be halted.
Bagging a set of overfitting trees can successfully combat the overfitting each tree
presents. Such an ensemble of recursively grown trees is called a random forest.
The word “random” is because each tree uses a random portion of the original
data as training (which is sampled from the original dataset with replacement) and
only a random subset of input feature dimensions are sampled for viable split
points at each node in the trees





