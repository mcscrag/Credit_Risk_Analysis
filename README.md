# Credit_Risk_Analysis

## Purpose

### The purpose of this analysis was to compare the accuracy, precision, and sensitivity of a number of different supervised machine learning models in predicting credit risk of potential loan issuees.

## Results

The first four models were various methods of resampling data, while the last two were ensemble classifier methods. The following list shows the classification reports for each machine learning model's performance when ruin against the test data.

### 1. Naive Random Oversampling

![naive_random](/Resources/naive_random_oversampling.png)

### 2. SMOTE Oversampling

![smote](/Resources/smote_oversampling.png)

### 3. Cluster Centroids Undersampling

![undersampling](/Resources/cluster_centroids_undersampling.png)

### 4. Combination Over/Undersampling (SMOTEEN)

![smoteen](/Resources/smoteen_combination.png)

### 5. Balanced Random Forest Ensemble

![random_forest](/Resources/balanced_random_forest.png)

### 6. AdaBoost Classifier Ensemble

![naive_random](/Resources/adaboost_classifier.png)

## Summary

When trying to develop a model that will reliably identify high_risk borrowers, it is important to strike a balance between precision and sensitivity. While we do want to make sure we identify most of the high risk borrowers in order to reduce the risk of the lender giving out risky loans, we also don't want the model to be over sensitive and deny too many potential borrowers who would have otherwise been good customers.

Looking at the results, virtually all of the models tested in this analysis have very low precision for the high risk class of borrower. All of the resampling models had a precision of <0.01, while the ensemble classification models slightly impoved precision to 0.03 and 0.09. Additionally, the imbalanced accuracy score for the ensemble models were significantly better than the resampling methods, with the AdaBoost Classifier achieving an accuracy of nearly 90%. It's clear from the results that the first four resmampling methods would not be good models for this application since their accuracy scores were all below 50%.

Since the Adaboost Classifier model outperformed the Balanced Random Forest model in every metric, the question is should we recommend the use of this classifier algorithm for predicting credit risk?

As already noted, the accuracy is quite good at 87%. Yet the precision is low at just 10%. Additionally, the recall is very high at 92% for the minority class. This means that the model succesfully identified 92% of the actual high risk borrowers, but of all the flagged borrowers 90% of them were not actually high risk. I think it's fine to recommend this model for this application since the size of the minority class is so low (100 of 17,200 loans analyzed). This menas that even though 90% of the 100 flagged borrowers were not actually high risk, this represents just a small fraction of total borrowers and thus the potential loss avoided by the lender is justified.
