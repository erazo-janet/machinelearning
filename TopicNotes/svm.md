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
So you can draw a ton of lines to separate the points. but which one does a better job? Which one is optimal? Depends on the size of margin and distance from the hyperplane so we use:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/3b2ea018-414d-4885-9fda-a921c89cef7e)  

where b shifts the direction of the line. To find the separating hyperplanes with maximum margin, we need to find a set of parameters so that the region defined by b+xtq = +-1 with each translate just touching one of the two classes, has the largest margin.  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/5785c0f0-ccf9-48cf-b86c-783397cc7f7c)  

you can see here many different linear decision boundaries can perfectly separate a dataset. two linear decision boundaries are shown in green and black. the decision boundaries with maximum margin in black is the best choice.

### Finding the maximum margin
The margin can be determined by calculating the distance between any two points both lying on the normal vector w. denoting by x1 and x2 the points on vector w belong to the
positively and negatively translated hyperplanes respectively, with the margin computed as the length of the line segment connecting x1 and x2. The margin can be calculated by finding the difference between the two translation hyperplanes evaluated at x1 and x2 as  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/fecf35a7-70f2-4719-bf73-d828dc3d4c49)  

we can solve for the margin directly in terms of w as:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/745886f8-325a-4fe2-b0c2-25d2a7a9f9dc)  
  
  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/9f6fcf25-beba-4b21-92e9-e48334150463)  

^ the margin between two separating hyperplanes is calculated by measuring the distance between the two points of intersection of the nromal vector w and the two equidistant translations of the hyperplance. this has a distance of 2/ ||w||

in the image below, in the left you can see three boundaries learned via minimizing the margin-perceptron cost. each line is a different random minimzation. on the right, the decision boundary is computed by optimizing the soft margin SVM cost. The smv in the right provides the max margin contrary to the boundaries shown in the left. in the right the boundaties pass through the two classes - equidistant from the svm decision boundary. these points are called _support vectors_:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/8d849ed7-f274-4a70-a48b-cd3f265f03cc)  

Hard Margin and soft margin SVM problems: To find a separating hyperplane for the data with minimum length normal vector, we need to minimize ||w||2 subject to the constraints that the hyperplane perfectly separates the data as given by the margin criterion. This results in the hard margin support vector machine problem:  
Minimize ||w||2 subject to:   

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/bb4ae35b-9dc0-41a8-aea3-44a0ae7d15a1)  

we can solve the hard margin problem by relacing the constraints and then apply algorithms to minimize. this is the regularization approach, forming the cost function:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/69be1a7d-a081-4a84-8f85-25e15e62bd05)  
  
Which should be minimized. When l is a small positive number, we put more pressure on the cost function to make sure the constraint holds. When l is very small, the above formulation matches the original constrained form. This regularized form of the cost function is referred to as the soft-margin Support Machine cost.

### SMV and noisy data 
The soft-margin SVM is very helpful when the data has noise in and is not perfectly separable, which is a more likely case in practice. The hardmargin case cannot accommodate the noise while soft-margin relaxation can be properly minimized and hence, more practical

### Confidence Scoring
Once a decision boundary is learned, we can judge its confidence in any point based on the point’s distance to the decision boundary. Our classifier has zero confidence for the points lying along the decision boundary itself, because the boundary cannot tell us accurately which class such points belong to (that is the reason they are randomly assigned a label value if we need to make a prediction here). Also, near the decision boundary we have little confidence in the classifier’s prediction. This is because, with small perturbation, the point could shift to the other side of the decision boundary and hence, a different classification (label). Similarly, we have high confidence for the points away from the decision boundary, as these labels will not change if we perturb the point slightly or change the location of the decision boundary. Therefore, to measure the “confidence”, we need to compute the distance of the points to the boundary through the sigmoid function. This gives the confidence that a point belongs to, for example, class +1. The signed distance, d, from a point to a decision boundary can be computed
  
![image](https://github.com/erazo-janet/machinelearning/assets/76828004/1b0548c2-f6e4-4345-bd07-a2d3fb35f59f)

### Confusion matrix
Another method for judging the quality of a trained model is through the confusion matrix. A confusion matrix is a look-up table where classification results are broken down by actual (across rows) and predicted (across columns) class membership. Denoted by “A” the number of data points whose actual label, +1, is identical to the label assigned to them by the trained classifier. The other diagonal entry D is similarly defined as the number of data points whose predicted class, -1, is equal to their actual class. The off diagonal entries denoted by B and C represent the two types of classification errors wherein the actual and predicted labels do not match one another. In practice, we need these two elements to be as small as possible. Our accuracy metric can be expressed in terms of the confusion matrix quantities
alpha = a+d/a+b+c+d

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/d3f4f02f-8895-4ae8-8ce4-130c1c25681b) 

 in the photo above the confusion matrix was used to provide additional quality matrices for two class classification.  A confusion matrix is used to study performance of a classification model on a set of data for which the true values are known.

## Examples:

Example: Identifying disease
Consider two possible predicted classes on a training dataset for patients who are examined for a disease. This is “yes” (having the disease) or “No” (not having the disease). A total of 165 patients are examined for the presence of the disease. Out of 165 samples, we predict “Yes” 110 times and “No” 55 times. In our training sample, we know that 105 patients have the disease and 60 do not have the disease. 
  
The confusion matrix is formed as:
Predicted NO Predicted Yes
Actual NO 50 (TN) 10 (FP)
Actual Yes 5 (FN) 100 (TP)
  
True Positives (TP): We predict “Yes” (they have the disease) and they have the disease
True Negatives (TN): We predict ”No” (they do not have the disease) and they do not have the disease
False Positives (FP): we predict “Yes” (they have the disease) but they do not have the disease
False Negatives (FN): We predict “No” (they don’t have the disease) but they have the disease
  
Accuracy: (TP+TN)/Total (100+50)/165 = 0.91 Misclassifications: (FP+FN)/Total = (10+5)/165 = 0.09
True Positive rate: TP/Actual yes = 100/105 =0.95 False Positive Rate: FP/actual NO = 10/60 = 0.17

    
Example: Credit Check
Here we examine a two-class classification consisting of P=1000 samples extracted from loan applications. Each input has an associated label: good (700 examples) and bad (300 examples) credit risk. In learning a classifier for this dataset we create an automatic credit risk assessment tool that can help decide whether or not future applicants are good candidates for loans. The N=20 dimensional input features here include: the individual’s current account balance (feature 1), the duration (in months) of previous credit with the bank (feature 2), the payment status of any prior credit (feature 3), the
current value of their saving (feature 6) etc. Minimizing the Perceptron cost we can achieve a 75 percent accuracy over the entire dataset with the
following confusion matrix:

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/e712017f-aa41-408a-ac4d-58337eee84f0)


Example: Spam detection
Here we perform a two-class classification on a spam detection dataset. The data set consists of P=4601 data points, 1813 spam and 2788 ham emails, with each data point consisting of various input features as well as a binary label indicating whether or not the email is spam. By properly minimizing the softmax cost we can achieve 93 percent accuracy over the entire dataset with
the following confusion matrix:  

![image](https://github.com/erazo-janet/machinelearning/assets/76828004/d14ac458-44e6-4fcf-bc3c-a61655e44fd6)




