Challenge 20

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
* Explain what financial information the data was on, and what you needed to predict.
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

The purpose of this analysis is to analyze the data to establish a loan risk based on historical loans.  In reviewing the data, we will build a model to predict the risk of a loan.

The information we were provided was loan size, the interest rate, the borrower income, the debt to income ration, the number of acoutns, the number of derogatory marks, the total amount of debt and the loan status - whether the loan was healthy or high-risk.  Our model will be created to predict if the loan is healthy or high-risk. 

Value Counts were performed to get the total of healthy (0) and high-risk loans (1).  There were over 75,000 healty loans and only 2,500 high-risk loans.  The data was split into training and testing data using train_test_split.  The data is split into x and y test and train datasets.  The training data was then put into the logisic regression model by fitting the data.   A prediction was created with the x_test data and we evaluate this by getting a balanced accuracy score, confusion matrix and classification report.

These steps were repeated again after using a RandomOverSampler to give equal numbers to the data points.  The logistic regression model was used on the reampled data with the x_test data.  We again evaulate this prediction by getting a balanced accuracy score, confusion matrix and classification report.



## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.

  Model 1 is the logistic regression model using training data.
    *Balanced Accuracy Score: 0.9520479254722232
    *Confusion Matrix:  18663, 102, 56, 563
    *Precision: 0 - 1.00, 1 - 0.85
    *Recall: 0 - 0.99, 1 - 0.91
    *F1-Score: 0 - 1.00, 1 - 0.88
    *Accuracy: 0.99


* Machine Learning Model 2:
  Model 2 is the logistic regression model using resampled data.
    *Balanced Accuracy Score: 0.9936781215845847
    *Confusion Matrix:  18649, 116, 4, 613
    *Precision: 0 - 1.00, 1 - 0.84
    *Recall: 0 - 0.99, 1 - 0.99
    *F1-Score: 0 - 1.00, 1 - 0.91
    *Accuracy: 0.99

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.

Of the two machine learning models, I feel the Model 2 using the resampled data performs better as almost all the scores are higher than with the training data.  While it is more important to accurately predict the high-risk loans (1's), and the precision for the high-risk loans is higher for the training data (model 1), it is only slightly better (0.84 vs 0.85.).  Despite the importance of the precision score, the difference is only 1%.  In every other score, Model 2 performs better.  I do ultimately feel both are very good models for predicting loans. 
