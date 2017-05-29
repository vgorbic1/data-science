## Multiple Linear Regression with R
Use this [Demo data](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/50_Startups.csv)
1. Set the working directory
2. Preprocess data. Use a template or create a new one.
3. Encode categorical data
4. Split the dataset into the Training set and Test set
5. Fit Multiple Regression to the Training set
6. Get a prediction on the Test results.

The complete template:
```r
# Multiple linear regression Template

# Importing the dataset
dataset = read.csv('50_Startups.csv')

# Encoding categorical data
dataset$State = factor(dataset$State,
                         levels = c('New York', 'California', 'Florida'),
                         labels = c(1, 2, 3))

# Splitting the dataset into the Training set and Test set
# install.packages('caTools')
library(caTools)
set.seed(123)
split = sample.split(dataset$Profit, SplitRatio = 0.8)
training_set = subset(dataset, split == TRUE)
test_set = subset(dataset, split == FALSE)

# Feature Scaling
# training_set = scale(training_set)
# test_set = scale(test_set)

# Fitting Multiple Regression to the Training set
regressor = lm(formula = Profit ~ .,
## The dot (.) means all independent variables
    data = training_set)
## To check the regressor info put to the console the following:
## > summary(regressor)

# Predicting the Test set Results
y_pred = predict(regressor, newdata = test_set)
```

### Building the optimal model using Backward Elimination
```r
# Fitting Multiple Regression to the Training set
regressor = lm(formula = Profit ~ R.D.Spend + Administration + Marketing.Spend + State,
               data = dataset)
## To check the regressor info put to the console the following:
summary(regressor)
## If the P-value in one of the column is higher than significant level (0.05), take this column out and do it over
regressor = lm(formula = Profit ~ R.D.Spend + Administration + Marketing.Spend,
               data = dataset)
summary(regressor)
## If the P-value in one of the column is higher than significant level (0.05), take this column out and do it over
regressor = lm(formula = Profit ~ R.D.Spend + Marketing.Spend,
               data = dataset)
summary(regressor)
## If the P-value in one of the column is higher than significant level (0.05), take this column out and do it over
regressor = lm(formula = Profit ~ R.D.Spend,
               data = dataset)
summary(regressor)
## Done! The model is ready.
```
