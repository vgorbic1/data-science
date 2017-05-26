## A Simple Linear Regression (R)
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
                                        
### Creating the model with R
[Demo data](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/Salary_Data.csv) file.
1. Set a working directory.
2. Data preporcessing step. Use a template or create a new one:
```r
# Data Preprocessing Template

# Importing the dataset
dataset = read.csv('Salary_Data.csv')

# Splitting the dataset into the Training set and Test set
# install.packages('caTools')
library(caTools)
set.seed(123)
split = sample.split(dataset$Salary, SplitRatio = 2/3)
training_set = subset(dataset, split == TRUE)
test_set = subset(dataset, split == FALSE)
```
3. No feature scaling needed.
4. Fit simple linear regression to the data set
```r
regressor = lm(formula = Salary ~ YearsExperience, data = training_set)
```
*Salary ~ YearsExperience* means that salary is proportional to the years of experience.

On the IDE console type ```summary(regressor)``` to get all information about what is going on behind the scene.

5. Predicting the Test set results
```r
y_pred = predict(regressor, newdata = test_set)
```
6. Visualise the Training set results. Import and install *ggplot2* library.
Use it once and then comment out:
```r
install.packages('ggplot2')
```
Use the library:
```r
library(ggplot2)
```
Create the graph for the training set:
```r
ggplot() + 
  geom_point(aes(x = training_set$YearsExperience, y = training_set$Salary),
             color = 'red') +
  geom_line(aes(x = training_set$YearsExperience, y = predict(regressor, newdata = training_set)),
            color = 'blue') +
  ggtitle('Salary vd Experience (Training Set)') +
  xlab('Years of experience') +
  ylab('Salary')
```
Create the graph for the test set:
```r
ggplot() + 
  geom_point(aes(x = test_set$YearsExperience, y = test_set$Salary),
             color = 'red') +
  geom_line(aes(x = training_set$YearsExperience, y = predict(regressor, newdata = training_set)),
            color = 'blue') +
  ggtitle('Salary vd Experience (Test Set)') +
  xlab('Years of experience') +
  ylab('Salary')
```
This is the complete script:
```r
# Simple Linear Regression

# Importing the dataset
dataset = read.csv('Salary_Data.csv')

# Splitting the dataset into the Training set and Test set
# install.packages('caTools')
library(caTools)
set.seed(123)
split = sample.split(dataset$Salary, SplitRatio = 2/3)
training_set = subset(dataset, split == TRUE)
test_set = subset(dataset, split == FALSE)

# Feature Scaling
# training_set = scale(training_set)
# test_set = scale(test_set)

# Fitting Simple Linear Regression to the Training set
regressor = lm(formula = Salary ~ YearsExperience, data = training_set)

# Predicting the Test set results
y_pred = predict(regressor, newdata = test_set)

# Visualising the Training set results
install.packages('ggplot2')
library(ggplot2)
ggplot() + 
  geom_point(aes(x = training_set$YearsExperience, y = training_set$Salary),
             color = 'red') +
  geom_line(aes(x = training_set$YearsExperience, y = predict(regressor, newdata = training_set)),
            color = 'blue') +
  ggtitle('Salary vd Experience (Training Set)') +
  xlab('Years of experience') +
  ylab('Salary')

# Visualising the Test set results
ggplot() + 
  geom_point(aes(x = test_set$YearsExperience, y = test_set$Salary),
             color = 'red') +
  geom_line(aes(x = training_set$YearsExperience, y = predict(regressor, newdata = training_set)),
            color = 'blue') +
  ggtitle('Salary vd Experience (Test Set)') +
  xlab('Years of experience') +
  ylab('Salary')
```
