## Random Forest Intuition
Random forest is a version of Ensemble Learning. Ensemble learning is when multiple algorithms are taken or one algorithm
is taken several times.

Steps to execute Random Forest:
1. Pick at random K data points from the Training set.
2. Build the Decision Tree associated to these K data points.
3. Choose the number Ntree of trees you want to build and repeat steps 1 and 2.
4. For a new data point, make each one of your Ntree tees predict the value of Y for the data
point in question and assign the new data point the average across all of the predicted Y values.
