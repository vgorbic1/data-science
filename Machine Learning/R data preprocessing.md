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
