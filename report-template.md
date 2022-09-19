
## Overview of the Analysis

The purpose of this analysis was to use use machine learning and data-resampling to predict differentiaton between healthy or high-risk loans. This was performed using provided loan data categorized by: loan size, interest rate, income, debt-to-income, number of accounts, derogatory marks, and total debt. As part of the analysis, the value_counts function was used to determine the size of healthy loans compared to high-risk loans, which revealed that there was an imbalance: 75,036 healthy loans, and 2,500 high-risk loans. Imbalanced target categories may skew the model's performace, so the analysis proceeded with two sets of data: the original data, and data re-sampled with the RandomOverSampler. The resampling function augments the size of the smaller target set, so the resampled healthy and high-risk loans in the training data set were both sized at 56,271 entries. The LogisticRegression model was the model chosen to predict loan status in this exercise. The loan data was split into training and testing datasets. The model was instantiated and fit to both the original training data, and the resampled training data. The model then uses the testing features to predict healthy or high-risk loan status; this was done with both the original and resampled testing features. These predictions were compared against the actual loan statuses with balanced accuracy scores, confusion matrixes, and classification reports. 


## Results

Logistic Regression predictions with the original data:
    -Accuracy score: 95%
    -Precision score: 85%
    -Recall score:   91%


Logistic Regression predictions with the resampled data:
    -Accuracy score: 99%
    -Precision score: 84%
    -Recall score:   99%
    
    
## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

The results clearly demonstrate that oversampling the data with the RandomOversampler yields a better predictive model for loan status. This is shown specifically in the recall score: 91% with original data, and 99% with resampled data. Since a lender's concern is liability involved with high-risk loans, their goal is to identify these high-risk loans. Higher recall score means that there are less high-risk loans that go unflagged as such. Even though the resampled model scored 1 point lower with precision, this is of slim-to-nill concern for lenders, as a false flag of 'high-risk' can be investigated and re-determined to be a healthy loan. Conversely, missing a high-risk flag on a borrower will lead to high-risk loans and increased liability.
