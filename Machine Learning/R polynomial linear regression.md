## Polynomial Linear Regression with R
Sample [Dataset](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/Sample%20Data/Position_Salaries.csv)
1. Set the working directory where the dataset resides.
2. Import the dataset.
3. No need to split data to training and test data for this particular dataset (database is too simple/small).
4. No need for Feature Scaling either.
5. Fit a linear Regression to the dataset. (optional)
6. Fit a polynomial Regression to the dataset.
7. Compare two regressions. (optional)
```r
# Polynomial Linear Regression Template

# Importing the dataset
dataset = read.csv('Position_Salaries.csv')
dataset = dataset[2:3] # Keep only those columns that needed

# Splitting the dataset into the Training set and Test set
# install.packages('caTools')
# library(caTools)
# set.seed(123)
# split = sample.split(dataset$DependentVariable, SplitRatio = 0.8)
# training_set = subset(dataset, split == TRUE)
# test_set = subset(dataset, split == FALSE)

# Feature Scaling
# training_set = scale(training_set)
# test_set = scale(test_set)

# Fitting Linear Regression to the dataset
lin_reg = lm(formula = Salary ~ .,
             data = dataset) 
## Take a quick look by typing "summary(lin_reg)" in console

# Fitting Polynomial Regression to the dataset
dataset$Level2 = dataset$Level^2 # Create a new column with squares
dataset$Level3 = dataset$Level^3 # Create a new column with qubes
dataset$Level4 = dataset$Level^4 
poly_reg = lm(formula = Salary ~ .,
              data = dataset)

# Visualise Linear Regression
ggplot() + 
  geom_point(aes(x = dataset$Level , y = dataset$Salary),
             color = 'red') +
  geom_line(aes(x = dataset$Level , y = predict(lin_reg, newdata = dataset)),
            color = 'blue') +
  ggtitle('Truth or Bluff (Linear Regression)') +
  xlab('Level') +
  ylab('Salary')

# Visualise Polynomial Regression
ggplot() + 
  geom_point(aes(x = dataset$Level , y = dataset$Salary),
             color = 'red') +
  geom_line(aes(x = dataset$Level , y = predict(poly_reg, newdata = dataset)),
            color = 'blue') +
  ggtitle('Truth or Bluff (Polynomial Regression)') +
  xlab('Level') +
  ylab('Salary')

# Predicting a new result with Linear Regression
## Predict a single level only
y_pred = predict(lin_reg, data.frame(Level = 6.5))

# Predicting a new result with Polynomial Regression
y_pred = predict(poly_reg, data.frame(Level = 6.5,
                                      Level2 = 6.5^2,
                                      Level3 = 6.5^3,
                                      Level4 = 6.5^4))
```
