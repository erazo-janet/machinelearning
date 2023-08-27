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
