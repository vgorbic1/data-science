## Multiple Linear Regression
Multiple linear regression is calculated by a similar formula as a simple linear regression, but with several
coefficient and independent variagles:
### y = b<sub>0</sub> + b<sub>1</sub>*x<sub>1</sub> + b<sub>2</sub>*x<sub>2</sub> + ... + b<sub>n</sub>*x<sub>n</sub>
Where:
- y is a dependend variable
- x are independent variables
- b<sub>0</sub> is a constant
- b<sub>1</sub> - b<sub>n</sub> are coefficients

If you have a categorical data as your independent variable, use dummy variables, but remember of the dummy variable trap
(always omit one dummy variable in your formula)

### Building a Model
Five methods of building models:
1. All-in. Throw all your variables, if you know for sure that each and every of them is important.
2. Backward Elimination. (The fastest)
- Select a significance level to stay in the model (SL = 0.05)
- Fit the full model with a ll possible predictors
- Consider the predictor with the highest P-value. If P > SL, go to the next step, otherwise go to the last step.
- Remove the predictor
- Fit model without this variable. Go back if you need
- Model is ready
3. Forward Selection
- Select a significance level to enter the model (SL = 0.05)
- Fit all simple regression models Y ~ X<sub>n</sub> Select the one with the lowest P-value
- Keep this variable and fit all possible models with one extra predictor added to the one(s) you already have
- Consider the predictor wiht the lowest P-value If < SL go to previous step, otherwise go the last step.
- Take the variable you just added. The model is ready.
4. Biderectional Elimination (Stepwise Regression)
- Select a significance level to enter and to stay in the model (SL ENTER = 0.05, SL STAY = 0.05)
- New variable must have P < SL Enter to enter)
- Old variables must have P < SL STAY to stay)
- No new variables can enter and exit. The model is ready.
5. Score Comparison
- All possible models. Most tedious. If you have 10 columns of data -- it is 1,023 models!
