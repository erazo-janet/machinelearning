# Credit Card Fraud Detection System using Decision trees
This is part of my project for PHYS 243 at UC Riverside.    
* You can view/download the Jupyter Notebook here:  
* You can view/download the python file here: 
  
The dataset utilized in this study was obtained from Kaggle which consists of credit card transactions made by European cardholders during the month of September 2013, provided in CSV format. This dataset includes transactions spanning just two days, resulting in a highly imbalanced dataset. Of the 284,807 transactions recorded, 492 represent fraudulent activities. The dataset is characterized by several columns, including the time between each transaction, the monetary value of each transaction, and class. A ‘class’ value of 1 indicates a fraudulent transaction, while 0 signifies a legitimate one. In addition to these columns, the dataset includes a set of numerical input variables, labeled as “V1” through “V28”. These features are the result of the Principal Component Analysis (PCA), which is a dimensionality reduction technique that transforms original features into a set of linearly uncorrelated variables, known as principal components. This is used to anonymize the data and protect the cardholder's confidentiality. Viewing the dataset manually could take a long time to analyze which transactions are fraudulent. With the use of machine learning, we can use data processing and machine learning techniques such as a decision tree to create an effective fraud detection model.

The decision tree model is split into these steps:  
* data prep - importing file and creating dataframe, transform data
* create decision tree
* visualize percision recall
* visualize the tree
  
