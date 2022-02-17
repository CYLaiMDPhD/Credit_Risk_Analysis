# Credit_Risk_Analysis

*Note: This repository was created to fulfill an assignment (Module 17 Challenge) for the UC Berkeley Data Analytics and Visualization Bootcamp. Submitted on 2-17-22 for grading.*


## Overview
This report presents analyses of a set of historic loan data in order to calculate credit card risk for individuals. Six different machine learning algorithms from the Scikit Learn module were applied to the data set and their results are compared below. The data set was highly imbalanced, making predictions of high risk loans more difficult.

**Data Source:**
Loan dataset (not included in this repository due to size) was provided as part of course materials as a csv file.

---

## Results

Four methods of data resampling with logistic regression and two ensemble algorithms were applied to the data set provided, which consisted of 68,817 records with 85 features after data cleaning and encoding. Low risk loans (68,470) vastly outnumbered high risk loans (347). 

Figures 1 through 5 below show the classification score results for each method.

**Figure 1: Balanced Classification Scores for Data Analyzed by Random Oversampling and Logistic Regression**

![ROS.png](/Images/ROS.png)


**Figure 2: Balanced Classification Scores for Data Analyzed by SMOTE Oversampling and Logistic Regression**

![SMOTE.png](/Images/SMOTE.png)


**Figure 3: Balanced Classification Scores for Data Analyzed by Cluster Centroid Undersampling and Logistic Regression**

![CC.png](/Images/CC.png)


**Figure 4: Balanced Classification Scores for Data Analyzed by Combination Sampling (SMOTEENN) and Logistic Regression**

![smoteenn.png](/Images/smoteenn.png)


**Figure 5: Balanced Classification Scores for Data Analyzed by Balanced Random Forest Classifier**

![BRF.png](/Images/BRF.png)


**Figure 6: Balanced Classification Scores for Data Analyzed by Easy Ensemble AdaBoost Classifier**

![EE.png](/Images/EE.png)



Table 1 below displays the accuracy score, precision, and recall for predicting high risk loans by the six methods used.

**Table 1: Accuracy, Precision, and Recall Scores for Predicting High Risk Loans**

| Model | Random Oversampling | SMOTE | CC Undersampling | Combination Sampling (SMOTEENN) | Random Forest | Easy Ensemble |
|---|---|---|---|---|---|---|
|Accuracy Score|0.608|0.620|0.539|0.565|0.788|0.925|
|Precision|0.01|0.01|0.01|0.01|0.04|0.07|
|Recall|0.59|0.55|0.66|0.57|0.67|0.91|


Based on the data above, we can draw the following general observations:
- All methods predicted low risk loans with high accuracy and precision, which is unsurprising given the highly imbalanced data set (Figures 1-6).
- Overall, all methods yielded very low precision scores for predicting high risk loans, which is again unsurprising given the imbalanced nature of the data set. 
- Among the resampling methods, Cluster Centroid Undersampling yielded the best recall score, but the lowest accuracy score (Table 1). 
- Both ensemble methods (Random Forest Classifier and Easy Ensemble Classifier) gave better accuracy, precision, and recall scores than the resampling methods.
- The Easy Ensemble algorithm in the SciKit Learn module yielded the best accuracy, precision, and recall scores compared to all other methods used (Table 1).



___


## Summary

This data set was highly imbalanced for low risk loans. Therefore, resampling the data prior to training a logistical regression model was necessary. Ensemble methods can also applied. The low precision scores for high risk loans is not surprising given the overwhelming number of actually low risk loans that by be falsely classified as high risk within the data set. The accuracy and recall scores may be more useful in the case to evaluate the best algorithm. All methods producted accuracy and recall scores above 50% with the two ensemble methods outperforming the resampling plus logistic regression methods. The Easy Ensemble decision tree method produced the best results with 92.5% accuracy and a recall score of 0.91 for high risk loans. This indicates that the method is highly sensitive for detecting high risk loans, even if it would flag many false positives. If a lending institution were interested in reducing the amount of bad loans, this would be a reasonable model to use. This would be desirable if the financial loss from bad loans would be greater than potential loss of profit from falsely classified good loans (actual low risk loans classified as false positives).




