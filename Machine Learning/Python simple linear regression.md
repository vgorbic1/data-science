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
- *y<sup>^</sup>* is prognosed position on the chart

Take the difference between real and prognosed positions and square the result. Sum the 
results for all pieces of data availale and find the minimum of that. 
                                        
### Creating the model with Python
[Demo dataset](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/Sample%20Data/Salary_Data.csv) file.
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
3. Fit Simple Linear Regression to the Training set. For that you need to import a Linear Regression class from sklearn library. Create an object of that class and fit data. This object is a *simple linear regression machine*. Train your model on the training set (the model will learn a corelation betwin X_train matrix and y_train vector) to predict the dependent variable.
```python
from sklearn.linear_model import LinearRegression
regressor = LinearRegression()
regressor.fit(X_train, y_train)
```
4. Predict the Test set results. Create a vector of predictions (y_pred):
```python
y_pred = regressor.predict(X_test)
```
5. Visualize the Training set results:
```python
plt.scatter(X_train, y_train, color = 'red')
plt.plot(X_train, regressor.predict(X_train), color = 'blue')
plt.title('Salary vd Experience (Training set)')
plt.xlabel('Years of Experience')
plt.ylabel('Salary')
plt.show()
```
6. Visualize the Test set results:
```python
plt.scatter(X_test, y_test, color = 'red')
plt.plot(X_train, regressor.predict(X_train), color = 'blue')
plt.title('Salary vd Experience (Training set)')
plt.xlabel('Years of Experience')
plt.ylabel('Salary')
plt.show()
```
This is the complete script:
```python
# Simple Linear Regression

# Importing the libraries
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd

# Importing the dataset
dataset = pd.read_csv('Salary_Data.csv')
X = dataset.iloc[:, :-1].values
y = dataset.iloc[:, 1].values

# Splitting the dataset into the Training set and Test set
from sklearn.cross_validation import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 1/3, random_state = 0)

# Feature Scaling
"""from sklearn.preprocessing import StandardScaler
sc_X = StandardScaler()
X_train = sc_X.fit_transform(X_train)
X_test = sc_X.transform(X_test)
sc_y = StandardScaler()
y_train = sc_y.fit_transform(y_train)"""

# Fitting Simple Linear Regression to the Training set
from sklearn.linear_model import LinearRegression
regressor = LinearRegression()
regressor.fit(X_train, y_train)

# Predicting the Test set results
y_pred = regressor.predict(X_test)

# Visualising the Training set results
plt.scatter(X_train, y_train, color = 'red')
plt.plot(X_train, regressor.predict(X_train), color = 'blue')
plt.title('Salary vs Experience (Training set)')
plt.xlabel('Years of Experience')
plt.ylabel('Salary')
plt.show()

# Visualising the Test set results
plt.scatter(X_test, y_test, color = 'red')
plt.plot(X_train, regressor.predict(X_train), color = 'blue')
plt.title('Salary vs Experience (Test set)')
plt.xlabel('Years of Experience')
plt.ylabel('Salary')
plt.show()
```
