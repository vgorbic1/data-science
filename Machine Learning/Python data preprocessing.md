## Data Preprocessing Using Python Language

### Importing Libraries
- Import Numpy library, that contains mathematical tools. Create a shortcut.
- Import a sub-library Pyplot from Matplotlib library to plot nice charts. Create a shortcut.
- Import Pandas library, which imports and manages datasets. Create a shortcut.
```python
import numpy as np
np.set_printoptions(threshold = np.nan)
import matplotlib.pyplot as plt
import pandas as pd
```
### Importing Project Data Set
- Specify a working directory. The working directory should contain a CSV file with the data set.
- Using Anaconda Spider as IDE on Windows just run the .py file (F5) in the directory wher the CSV file is located.
- Import data using *Pandas* library:
```
import os
os.chdir('full/path/to/working/directory')
dataset = pd.read_csv('Data.csv')
```
Create  a *Matrix of features*, which is a table of independent variables as columns and observations as rows:
```
X = dataset.iloc[:, :-1].values
```
In `[:, :-1]` the first variable `:` means ALL rows, and the second variable `:-1` means all the columns, except the last one.

Create a *Dependent variable vector*, which is a column of dependent variables an rows of observateions:
```
Y = dataset.iloc[:, 3].values
```
### Dealing with Missig Data
To compensate for missing data, take a mean of the column. Import the *Imputer* class from scikit-learn (a free software machine learning library for the Python) first. Then, create an object of that class:
```python
from sklearn.preprocessing import Imputer
imputer = Imputer(missing_vlaues = 'NaN', strategy = "mean", axes = 0)
```
Impute the matrix of data:
```python
imputer = imputer.fit(X[:, 1:3]) // means indexes of 2 and 3 of the columns
X[:, 1:3] = imputer.transform // replace the missing data by the means (average) of the columns
```
