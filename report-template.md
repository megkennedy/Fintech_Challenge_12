# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
The purpose of this analysis was to create a model that could predict high risk loans in a loan portfolio.
* Explain what financial information the data was on, and what you needed to predict.
The financial data provided was:
    Loan Size
    Interest Rate
    Borrower Income
    Number of Accounts
    Derogatory Marks
    Total Debt
    Loan Status(whether is was considered high risk or not)
I needed to train the model to predict the Loan Status
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
In the data file I was given the healthy loans totaled: 75,036 and the high risk loans totaled: 2,500.
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).
The begining of any machine learning is to prepare the data for the model. I separated the data into two variables:
y=loan status, and X=everything else. I further split the data into training and testing groups. I fit the training data to a Logistic Regression Model and then used that model to predict the loan status of the testing data. After analyzing that model I resampled the data using a random over sampler and once again fit it to a Logistic Regression Model. I then used the new model to predict the test data and analyzed the results.

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.
    * Balanced Accuracy Score: .9520
    * Precision:
        * Healthy Loans: 1.00
        * High Risk Loans: .85
    * Recall:
        * Healthy Loans: .99
        * High Risk Loans: .91

* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.
    * Balanced Accuracy Score: .9937
    * Precision:
        * Healthy Loans: 1.00
        * High Risk Loans: .84
    * Recall:
        * Healthy Loans: .99
        * High Risk Loans: .99
## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

The first model took the data as it was provided and came up with a fairly good model. In general, the first model has good accuracy, precision, and recall scores. However, in the second model we over sampled the high risk loan numbers when training the model, and as a result we got a slightly better model for the problem we were looking at. The second model increases the high risk loans recall score by 8%, while only loosing 1% in the high risk loan precision score. Since we are trying to identify high risk loans in our portfolio we would rather have false negative than false positives. If you look at the confusion matrix in the coding notebook, you will see that the false positives in model one is 56, while model 2 only had 4. Since high risk loans will likely be reviewed by a person it is more helpful for the model to pull more false negatives since it is unlikely the loans deemed healthy will be reviewed.

The first model is not a bad model; the second model just fits our problem better.

If you do not recommend any of the models, please justify your reasoning.
