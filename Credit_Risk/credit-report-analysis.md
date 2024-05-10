# Credit Report and Loan-Standing Analysis

## Overview of the Analysis

In order to better predict the status of future loans so our company can take the appropriate action, I've analyzed provided data on a large sample of loans via machine learning methods to determine whether any of these machine learning modules can assist us with our goal. The data provided ananymous account information for borrowers, showing such infromation as borrower income, the size and interest rate of their loan, whether they had any derogatory marks, and a debt-to-income ratio for the borrower, among a few other metrics. This data also provided information on whether or not the borrower's loan was considered healthy, or high risk. 

By pulling out the loan status from the data, we can utilize the remaining factors in a machine learning model to train the model into finding any potential patterns within those factors that then lead to the outcome as described by the current loan status. We can split the data into training and testing segments to see how well the model understood the data provided - we went with a 75/25 split for training versus testing data. 

Once we had the data split, we fit the training data onto the model, then made predictions using the testing data. Since we already know the true outcomes of the testing data (remember that we have the loan status for all the data provided), we can compare the predicted results against the actual results using tools called the Confusion Matrix and the Classification Report. These tools will provide insight with how accurate the model was in predicted the different outcomes for a loan when analyzing the collection of factors provided (resulting in a either a "healthy" or "high-risk" classification).

In the interest of comparing performance among several available machine learning models, I analyzed the data with the following algorithms:

- Logistic Regression
- Decision Tree
- Random Forest


## Results

Using bulleted lists, describe the accuracy scores and the precision and recall scores of all machine learning models.

* Logisitc Regression Model:
    * Overall Accuracy: 99%
    * Healthy Loan Precision/Recall: 100%/100%
    * High-Risk Loan Precision/Recall: 87%/95%

* Decision Tree Model:
    * Overall Accuracy: 99%
    * Healthy Loan Precision/Recall: 99%/100%
    * High-Risk Loan Precision/Recall: 87%/81%

* Random Forest Model:
    * Overall Accuracy: 99%
    * Healthy Loan Precision/Recall: 100%/100%
    * High-Risk Loan Precision/Recall: 88%/88%

## Summary

As we can see from the results, all three models provided 99% accuracy in correctly classfying loans from the test data. It is important, however, to dig into the details of the precision and recall results. Precision indicates what percentage of the loans classified a certain way were actually of that type, while recall gives a percentage of how many loans of that type were successfully identified by the model in comparison to the true total.

Our analysis indicates that healthy loans are simple for all of the models to identify, but that high-risk loans can cause the models more trouble. Importantly, we want the company to be able to identify potentiall high-risk loans early in order to take action, so the results for high-risk precision and recall are more important to us.

When keeping these ideas in mind, we can see that overall, the Logistic Regression model had the best results. It did not have the best precision score at 87%, but was only 1% off from the best-performing model analyzed. This indicates that while the model sometimes incorrectly classified a loan as high-risk, it still was correct 87% of the time. More impressively, the Logistic Regression model had a 95% recall performance, meaning that it found 95% of the high-risk loans within the testing data. This was sigificantly better recall performance compared to both the Decision Tree and Random Forest models.

Although the sub-90% performance in precision for high-risk loans could be worrisome, from a business perspective, this is likely an acceptable scenario; in these cases, we may provide additional information to borrowers about their options to keep their loans in good standing, while in reality, the borrower will not actually need any support. This is far more desirable than the opposite, where we fail to identify actually risky loans before it is too late.

Due to the total number of healthy loans in comparison to high-risk loans, there is a potential issue with the model "overfitting" the data, meaning that it becomes too specific in its results to the training data provided and cannot be relied on when new data is introduced. I do not think this will pose a problem for this model, especially if we make efforts to update the model at some regular interval. This will help introduce additional high-risk loan scenarios that the model can learn from, likely improving future performance.

Based on the results of this analysis, I would recommend the company considers using the Logistic Regression model to help predict the outcome of future loans. It would be helpful to update the model on a quarterly basis with additional data, as this could help improve the precision and recall scores for high-risk loan identificaiton over time.
