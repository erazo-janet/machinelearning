# Supprot Vector Machine  

Support Vector Machine (SVM) is a supervised machine learning algorithm that is used for classification and regression purposes. It is based on the idea to find a hyperplane that best separates two classes of data. It provides insights into the two class classification process under the assumption that data are linearly separable. Support vectors are data points closest to the hyperplane. If removed, they change the location of the hyperplane. Hyperplanes are the lines that divide the two calsses of data. The further from the hyperplane the data lies, the more confident we are that the classification is correct. Hyperplanes should be determined so that the data are as far away as possible from them.

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/384ac795-0462-447e-8f6d-cc8e35a4018c)  

### Margin Perceptron
The Margin Perceptron extends the basic Perceptron algorithm by introducing the notion of margin, which is the distance between the decision boundary (hyperplane) and the nearest data point. The Margin Perceptron aims to maximize this margin while still correctly classifying the training data. This emphasis on maximizing the margin can lead to better generalization and improved robustness compared to the standard Perceptron. The margin perceptron cost is:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/bd7c71f5-70f0-4b20-a2fd-1e39d5aae6f6)  

This is similar to the original perceptron cost. The difference is the “one” added to this sum. This additional “1” prevents the issue of a trivial zero solution with the previous Perceptron. That issue does not appear here.

### Finding the Hyperplane
Consider the training dataset points (x1,y1),(x2,y2),....(xn,yn)  
with y being either -1 or +1. We define the hyperplane as w^tx - b = 0. we need to find w & b to find the best maximum. So we need to maxmize teh distances for y +- 1.  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/3ad9b14d-15cc-4c47-ab54-97bf5f368b00)  

Here we have 2 parallel hyperplanes that separate the two classes of data so the difference between them is as large as possible. The regions bounded by the two hyperplanes is called the _ hardmargin_ and the max margin hyperplane is the hyperplane that lies halfway between the,/

### Soft Margin
The goal is to minimize:   

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/289d2215-816d-4be0-ba6f-14dbac58a1e1)  

if x is in the correct side of the margin, we get zero. if its in the wrong side, the max would be a postivie number corresponding to the distance. if the distance is amll, its more complicated.  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/3a92bc6d-97f3-4071-94c1-d6bedb0d9477)

here we have Two spaced translates of a separating hyperplane that just touch each respective Class, defines the margin of that separating hyperplane.

### Maximum Margin Decision Boundary

