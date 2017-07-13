## Grid Search
Grid Search allows to make a decision on which parameter to select when one makes a machine learning model. Or
what is the optimal value of those hyperparameters. Or, broadly, which machine learning to choose in oreder to
solve a business problem.

### How to choose a model
Which problem do you have?
- Regression
- Classification
- Clustering
Look at your dependent variable(s):
- No dependent variable - **Clustering**
- If you have a dependent variable(s):
1. if it is a continues (numerical) outcome - choose **Regression**
2. if it is a categorical outcome - choose **Classification**

Is my problem a linear or nonlinear problem?
- if yes - choose SVM (classification)
- if not - kernel SVM
But more precisely the Grid Search will answer it.
