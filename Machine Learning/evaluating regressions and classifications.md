## Evaluating Regression Models

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

## Evaluating Classification Models
Pretty much the same aspects as above, plus:
- *Logistic Regression* or *Naive Bayes* when you want to rank your predictions by their probability. For example if you want to rank your customers from the highest probability that they buy a certain product, to the lowest probability. Eventually that allows you to target your marketing campaigns. And of course for this type of business problem, you should use Logistic Regression if your problem is linear, and Naive Bayes if your problem is non linear.
- *SVM* when you want to predict to which segment your customers belong to. Segments can be any kind of segments, for example some market segments you identified earlier with clustering.
- *Decision Tree* when you want to have clear interpretation of your model results.
- *Random Forest* when you are just looking for high performance with less need for interpretation.
