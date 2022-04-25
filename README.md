# Credit_Risk_Analysis

## Overview
Calculating credit risk is difficult, because the number of good loans greatly exceeds the number of risky loans. This creates an unbalanced classification problem. Utilizing data from LendingClub, this analysis creates multiple models using resampling. I created models using the following resampling methods: 
* random oversampling
* SMOTE algorithm (oversampling)
* ClusterCentroids algorithm (undersampling)
* SMOTEENN algorithm (over- and undersampling)
* Balanced Random Forest Classifier (machine learning)
* Easy Ensemble Classifier (machine learning)
In this written report, I'll evaluate these resampling models and make a recommendation as to which model is the most effective at identifying credit risk. 

## Oversampling 
Random oversampling of the data returned the following results: 
![Random Oversampling](https://user-images.githubusercontent.com/93888037/165002208-35520d97-3002-4930-b3ce-264b2bd820d5.png)
The precision score was very high (99%), however the sensitivity was much lower (60%). This indicates a more conservative process in which very few high risk candidates are offered loans. However, there may be a large number of low risk candidates who are denied. 

Oversampling using the SMOTE algorithm returned the following results: 
![SMOTE Oversampling](https://user-images.githubusercontent.com/93888037/165002331-39a6336d-6b0a-4bc1-b157-62810cd7a94a.png)
The scores for SMOTE oversampling were very similar. This algorithm returned a 99% precision rating, with a 68% sensitivity rating. These numbers are more balanced, but may return a similar result as random oversampling. 

## Undersampling 
Random undersampling of the data returned the following results: 
![Random Undersampling](https://user-images.githubusercontent.com/93888037/165002387-137da89f-1a71-499f-b4da-b51b267ce7da.png)
Although the overall precision and sensitivity ratings are similar to resampling using the SMOTE algorithm, we can see that the random undersampling returned less true negative and false positive results than the SMOTE algorithm.

## Combination Over- and Undersampling (SMOTEENN)
![Combination Sampling](https://user-images.githubusercontent.com/93888037/165002604-4205bfb8-39b6-406b-a011-a887955a216d.png)
This test had a low accuracy score and somewhat similar precision and sensitivity scores. However, credit lenders may find this option appealing because of the Confusion Matrix results. This method returned an outstandingly low number of False Positive results (25). This means that very few risky candidates would be receiving loan offers. 

## Machine Learning 

Utilizing the random forest classifier returned the following results: 
![Random Forest Classifier](https://user-images.githubusercontent.com/93888037/165002688-5e44fc6a-bcd5-4b20-be43-eac006f51540.png)
This method returned very interesting results. The test had a slightly-better-than-average accuracy score (64%). However, the number of false negative results is extremely low. In fact, the true negative, false positive, and false negative columns are all very low. This model has a very low sensitivity rating (29% for high risk candidates). This could indicate a very conservative model.

It may also be useful to run the Random Forest Classifier to get a glimpse at the most important features when evaluating risk. In this ranking, we can see that the amount and interest rate of the loan are the most important features. 

![Features in Order](https://user-images.githubusercontent.com/93888037/165002918-2d7d31aa-4be8-49db-9f90-41a573c08c7d.png)



Utilizing the Easy Ensemble Classifier returned the following results: 
![Easy Ensemble Classifier](https://user-images.githubusercontent.com/93888037/165002877-c45d83bf-c0a7-4f62-9439-d093bf493bfe.png)
This machine learning method returned a much more balanced result than the random forest classifier. We can see an accuracy score of 85%, with a relatively small number of false positive and false negative results. This could indicate that the company stands  to lose a small number of low-risk clients. The test returned very low precision for high risk candidates. This could mean that a classification of high-risk is unreliable. 


## Overall Findings and Recommendation
Each of these models has drawbacks when determining credit worthiness especially when it comes to the very different precision and sensitivity scores. 

I would recommend a client utilizes the Easy Ensemble Classifier for this analysis. This model had a high accuracy score. Additionally, the number of False Positive results was very low. In lending, false positive results can be hugely damaging and can lead to large numbers of high-risk candidates receiving loans they are unable to repay. The Easy Ensemble Classifier seems to mitigate the most risk from the data set. 
