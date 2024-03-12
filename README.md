# Credit-Risk-Classification - Evaluating the Creditworthiness of Borrowers

![image](https://github.com/meehal0203/credit-risk-classification/assets/146681542/fb49daf1-5b85-4f53-82f0-65d4d69e25b0)


## Analysis Overview

In this analysis I will use various techniques to train and evaluate a model based on loan risk. The dataset used is historical lending activity from a peer-to-peer lending services company and the end goal is to determine the credit-worthiness of borrowers and place them into one of two classifications-
* A value of 0 means that the loan is healthy
* A value of 1 means that the loan has a high risk of defaulting

After examining the data and performing a statistical analysis, it was determined that 77536 loans were in the dataset - of these 75036 fell into the ‘Healthy’ loan category while only 2500 were in the ‘High Risk of Default’ category. This difference  indicates a potential that the model would predict loan status as healthy better than being able to predict loan status as non-healthy, due to the imbalance in available data.

I split the data into Training and Testing Sets and then fit a Logistic Regression Model with the original dataset and then generated a confusion matrix and classification report for the testing data.

## Results

The following Data Frame shows a summary of the Confusion Matrix results:
![image](https://github.com/meehal0203/credit-risk-classification/assets/146681542/0a64d3a0-a2be-4b86-9d68-39505f3008fb)




* As can be seen above, predicting low risk loans is much easier than predicting higher risk loans that are likely to default.
* The Classification Report is below, showing accuracy, sample size and two very important metrics used in statistical analysis, precision and recall.






![image](https://github.com/meehal0203/credit-risk-classification/assets/146681542/d6d6957a-5dcc-4125-8b53-434e59103810)


* Healthy Loans can be predicted with almost 100% accuracy across both precision and recall 
* Loans with a high risk of defaulting are a little harder to predict with only 85% precision and 91% recall figures - this means that there is increased likelihood of the data having false positives and negatives when predicting non-healthy loans than healthy ones
* Comparing the support size in the classification score shows that there is indeed a huge imbalance between the amount of data for each variable



## Summary

* The model seems to perform well according to the accuracy score of 99%, however this may be attributed to the data having a huge imbalance. The number of healthy, low-risk loans far outweighs the number of non-healthy, high risk loans by a ratio of ~30:1, indicating that the model would predict loan status’ as healthy better than being able to predict loan status' as non-healthy.
*  After running a model to set the sample size of each loan type to 2500, the accuracy scores for each set were higher than 99%. By undersampling the majority class to balance the dataset, we improve the model's ability to learn from the minority class, which may lead to better precision, recall, and F1-score for class 1. However, it's important to note that undersampling may also lead to a loss of information from the majority class, which could impact the model's ability to generalize.
* The 9% recall rates for  healthy loans being identified as a non-healthy loan might be somewhat costly for a lending company as it may cause the loss of customers but will remain minimal since they have not provided any funds to the customer. Having a precision rate of 86% for predicting non-healthy loans which are identified as a healthy loan might surely be more costly for a lending company due to the money being given to a customer who is unable to repay the loan.
* Overall, the model works relatively well, especially for low-risk loans, with high precision and recall values. However, it has a lower precision and recall for high-risk loans, indicating some room for improvement in predicting these cases. I would recommend using the model but only after ensuring that the sample size of high and low risk loans are more even. This more evenly distributed sample will lessen the chances of giving loans to individuals who would be at risk of defaulting.
