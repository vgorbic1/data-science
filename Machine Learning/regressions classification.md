## Regressions Classification

Regression Model | Pros | Cons
--- | --- | ---
Linear Regression | Works with any dataset sizes | Linear (direct) assuptions only
Polynomial Regression | Works with any dataset sizes. Works with non-linear problems | Need to calculate correct polynomial degree of a good bias/variance tradeoff |
SVR | Works with non-linear problems | Require feature scaling
Decission Tree | Works on both linear and non-linear problems. No need for feature scaling | Poor results on small datasets
Random Forest | Works on both linear and non-linear problems. Powerfull and accurate | Require to choose the number of trees

From [superdatascience.com](http://superdatascience.com)

### How to get a right model?
- Figure out whether your problem is linear or non-linear.
- If linear and has only one feature, go for Simple Linear Regression.
- If linear and has many features, go with Multiple Linear Regression.
- If non-linear, check k-Fold Cross Validation for best results.
