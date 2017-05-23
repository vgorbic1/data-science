## Data Preprocessing Using R Language

### Importing Libraries
All libraries (packages) needed are selected by default.

### Importing Project Data Set
This is a sample [Data Set](https://github.com/vgorbic1/data-science/edit/master/Machine%20Learning/Data.csv)

In RStudio go to the directory with your data set. Click on `More > Set as working directory` in the 'Files' tab. Import data set:
```
dataset = read.csv('Data.csv')
```

### Dealing with Missig Data
To compensate for missing data, take a mean of the column. Take care of each column separately:
```r
dataset$Age = ifelse(is.na(dataset$Age),
       ave(dataset$Age, FUN = function(x) mean(x, na.rm = TRUE)),
       dataset$Age)

dataset$Salary = ifelse(is.na(dataset$Salary),
       ave(dataset$Salary, FUN = function(x) mean(x, na.rm = TRUE)),
       dataset$Salary)
```

### Encoding Categorical Data
Factor function transforms categorical data to numerical data (*c* - is a vector):
```r
dataset$Country = factor(dataset$Country, 
      levels = c('France', 'Spain', 'Germany'), 
      labels = c(1, 2, 3))
dataset$Purchased = factor(dataset$Purchased, 
      levels = c('No', 'Yes'), 
      labels = c(0, 1))
```

### Splitting dataset into a training set and test set
Import *caTools* library to make a good split into training and test sets:
```r
install.packages('caTools')
```
Install the library only once. After that you can comment this line.

Use the library:
```r
#install.packages('caTools')
library(caTools)
```
Make the split. Set the seed (random number to randomise the dataset):
```r
set.seed(123)
split = sample.split(dataset$Purchased, SplitRatio = 0.8)
training_set = subset(dataset, split == TRUE)
test_set = subset(dataset, split == FALSE)
```
- *SplitRatio* is the percentage of learning set. 
- the *split* variable is an array of true or falls (depending if data was chosen or not).

### Feature Scaling
You have to scale all your feature variables (except dummies) to one range of numbers. Make sure all columns are numeric, do not include those that are not (do not include factors).
```r
training_set[, 2:3] = scale(training_set[, 2:3])
test_set[, 2:3] = scale(test_set[, 2:3])
```
