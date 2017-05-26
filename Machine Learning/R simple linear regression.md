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
1. Set a working directory
