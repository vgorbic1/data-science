## A Simple Linear Regression (Python)
Regression models (both linear and non-linear) are used for predicting a real value, like salary for example.

Simple Linear Regression formula on:
#### y = b<sub>0</sub> + b<sub>1</sub>*x
Where:
- *y* is a dependent variable (DV)
- *x* is an independent variable (IV)
- *b<sub>1</sub>* is a coefficient (a connector between *y* and *x*) 
- *b<sub>0</sub>* is the point where the line crosses the Y axis.

Example: salary to experience relevance:

The least squares method to calculate the best fitting linear regression:
#### SUM (y - y<sup>^</sup>)<sup>2</sup> -> min
Where:
- *y* is the real position on the chart
- *y<sup>^</sup> is prognosed position on the chart
Take the difference between real and prognosed positions and square the result. Sum the 
results for all pieces of data availale and find the minimum of that. 
                                        
### Creating the model with Python
[Demo data](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/Salary_Data.csv) file.
1. Preprocessing step. Use a preprocessed template below or create a new one. Set the working directory where your data resides.
```python
# SIMPLE LINEAR REGRESSION
# Data Preprocessing Template

# Importing the libraries
import numpy as np
np.set_printoptions(threshold = np.nan)
import matplotlib.pyplot as plt
import pandas as pd

# Importing the dataset
dataset = pd.read_csv('Salary_Data.csv')
X = dataset.iloc[:, :-1].values
y = dataset.iloc[:, 1].values

# Splitting the dataset into the Training set and Test set
from sklearn.cross_validation import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 1/3, random_state = 0)
```
2. The library automaically will take care of feature scaling.
3. Train your model on the training set (the model will learn a corelation betwin X_train matrix and y_train vector) to predict the dependent variable.
4. Test the performance of the machine learning model on the test set (X_test and y_test).
