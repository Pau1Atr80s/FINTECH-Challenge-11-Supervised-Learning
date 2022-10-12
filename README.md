# FINTECH-Challenge-12-Supervised-Learning

## Analysis Overview

Explain the purpose of the analysis.

*  The typical goal for a lending analysis is to minimize default risk.  The goal of this analysis is to minimize default risk using a dataset of historical lending activity.  


Explain what financial information the data was on, and what you needed to predict.

*  This analysis is using a large dataset of over 77,000 lending records.  The goal for this machine learning model is to predict which loans will be a high default risk, considering the credit default outcomes of the dataset.


Provide basic information about the variables you were trying to predict.

*  This dataset is imbalanced, in that the chance of credit default is inherently small compared to normal loan performance.  In this analysis, variable 0 identified a healthy loan, and variable 1 identified a high default risk loan.


Describe the stages of the machine learning process you went through as part of this analysis.

*  The first step of any machine learning analysis is to import and clean the data.  I then split the data into training and testing sets.  I then created a logistic regression model with the original data and evaluated the model’s performance across the set of metrics – accuracy, precision, recall, etc.  Upon review of the model’s initial performance, recall was low (there were too many false negatives).  In a lending environment, false negatives are the enemy.  This means that a model or underwriting process did not identify a high default risk.  For a lender, too many defaults can lead to poor company performance, compliance issues, and potential bankruptcy.


## Results

Machine Learning Model 1:

* ACCURACY:  95.2%
* PRECISION:  Identifying high default risk loans:  85%
* RECALL:  Identifying high default risk loans:  91%


Machine Learning Model 2:

* ACCURACY:  99.36%
* PRECISION:  Identifying high default risk loans:  84%
* RECALL:  Identifying high default risk loans:  99%


## Summary

The re-trained model with the over-sampled data helped the model increase its recall.  Overall, the accuracy went up after the re-training, which is good.  The precision stayed flat, which is acceptable in this scenario in which precision is not the most important metric.  The model was re-trained after balancing variables 0 and 1, which is essentially training the model on equal parts low default risk and high default risk.  This resulted in the model becoming adept at identifying high default risk and thus the increase in recall/90+% reduction in false negatives (from 56, down to 4).  From a lending perspective, we would rather err on the side of minimizing false negatives versus false positives.  If, in fact, we fail to lend to a customer who does not default, we can always find another customer.  Of course, we should avoid becoming too afraid of false negatives because that will hamper the growth of our loan portfolio.  A lender must be crystal clear about its desired return on the loan portfolio return and its risk appetite.

In conclusion, the random over-sampling method was effective in moving the model in the right direction – towards increasing recall to lower default risk.  Much more training would need to be done because there is a risk of overfitting when using the random over-sampling method.  Essentially, the model may become too familiar with the high default risk loans in the current dataset and fail to notice other reasons for high default risk and/or continue to predict too many false positives.  
