# OLS as a Line of Best Fit: Estimation versus Prediction

## Objective

In this lab, I used OLS regression to understand the difference between estimating relationships and making predictions.

## Methodology

- I fitted the same OLS regression using the closed form, statsmodels, and scikit-learn, and compared their coefficients.
- I added up to 100 random noise variables to examine changes in R-squared and adjusted R-squared.
- I split the California Housing data into training and test sets and fitted a regression model using eight predictors.
- I compared coefficient estimates and confidence intervals with test RMSE to understand the two uses of regression.
- I wrote a function called `holdout_rmse()` to calculate test RMSE for different sets of predictors.
- I removed districts at the housing value ceiling and fitted the eight-feature model again.

## Key Findings

The three OLS methods produced the same slope of 0.417938. R-squared increased from 0.4734 with no noise variables to 0.4758 with 100 noise variables. Adjusted R-squared did not increase in the same way.

The eight-feature model had a training RMSE of 0.7197 and a test RMSE of 0.7456. The AveRooms coefficient was -0.0381, with a 95% confidence interval of [-0.0430, -0.0333]. The model using median income alone had a test RMSE of 0.8421.

I also found that 965 districts were recorded at the housing value ceiling of $500,001. After removing these districts, the sample size decreased from 20,640 to 19,675. The test RMSE decreased from 0.7456 to 0.6511, and the regression coefficients changed.

These results show that adding variables can improve the fit on training data without improving predictions. They also show that changes in the sample can affect regression results. A statistically significant coefficient does not necessarily mean that a model predicts well.
