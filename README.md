# credit-risk-classification

In this Challenge, you’ll use various techniques to train and evaluate a model based on loan risk. You’ll use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

## Overwiew of Analysis

-The purpose of the analysis is to create and evaluate the accuracy of a data model that predicts the credit worthiness of potential borrowers from peer-to-peer lending services.


-The financial data the information was on the size of the loan:
   - Interest rate
   -  Borrower's income
   -  Debt to Income Ratio
   -  Number of accounts the Borrower held
   -  Derogatory marks against the borrower
   -  Total debt



The dataset (77,537 data points) was split into training and testing sets. The training set was used to build an initial logistic regression model (Logistic Regression Model 1) using the LogisticRegression module from scikit-learn. This Logistic Regression Model was then applied to the testing dataset. The purpose of the model was to determine whether a loan to the borrower in the testing set would be low- or high-risk and results are summarized below.

This intial model was drawing from a dataset that had 75,036 low-risk loan data points and 2,500 high-risk data points. To resample the training data and ensure that the logistic regression model had an equal number of data points to draw from, the training set data was resampled with the RandomOverSampler module from imbalanced-learn. This generated 56,271 data points for both low-risk (0) and high-risk (1) loans, based on the original dataset.

The resampled data was used to build a new logistic regression model (Logistic Regression Model (Resampled) ). The purpose of Logistic Regression Model (Resampled) was to determine whether a loan to the borrower in the testing set would be low- or high-risk having oversampled data. The results are summarized below.

* Logistic Regression Model (Original Data)
  * Precision: From the classification report we see that it predicts for a "healthy loan" with 100% precision, but with a "high-risk loan we have lower precision with 85%.
  * Accuracy: Overall was 99%
  * Recall: For the "healthy loan" the score was 99% and for "high-risk loans" the score was 91%.

* Logistic Regression Model (OverSampled Data)
  * Precision: The logistic regression model fit with oversampled data predicts "healthy loan" with 100% precision and predicts "High-risk loan" at 84%.
  * Accuracy: Overall 99%
  * Recall: For both the "healthy loans" and the "high-risk loans" the score was 99%

## Summary

From the results above both logistic regression models performed about the same when predicting "healthy loans" and "high-risk loans". The "Best" overall would be the logistic regression model with the original data, since it outperformed predicting "high-risk loan" compared to the oversampled data by 1%.

If our goal with this model was to predict "healthy loans" we would have hit a home run with either logistic regression models, but since our goal of this model was to predict the credit worthiness of potential borrowers from peer-to-peer lending services, the precision of both model being around 85% is not ideal since its predicting "high-risk loan" we woudl ideally want a precision score of above 95#.
