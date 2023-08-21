# Linear Two Class Classification
This is a supervised learning problem. In two-class classification the output of a dataset takes on only two discrete values or two classes. For example, object detection is such a process- you even detect an object or do not. Diagnostic of medical images is another kind of such process- either there is a malady or it is not.
The classification is different from regression where we have a continuous dataset. In regression, data comes in the form of P input/output pairs xp,yp  with each input xp is an N-dimensional vector. In classification, the corresponding output yp is no longer continuous but takes two discrete values. In the context of classification, the yp value the output takes is called _labels_ and all points sharing the same labels are called _class_0 of data

### Logistic Regression
This is a classification problem where the output can only take two values, like 0 &1 for example. It often gives poor fits. even introducing a step function does not provide a perfect fit to the data. Instead of tuning the parameters of a linear model and then passing the results to a step function, we can tune the parameters of a linear model after passing it through a step function.


