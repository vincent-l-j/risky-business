# Risky Business

![Credit Risk](image/credit-risk.jpg)

## Background

Mortgages, student and auto loans, and debt consolidation are just a few examples of credit and loans that people seek online.
Peer-to-peer lending services let investors loan people money without using a bank.
However, such investors need to mitigate credit risk.
This repo aims to predict credit risk using machine learning techniques.

Several machine learning models will be built and evaluated to predict credit risk.
Credit risk is an inherently imbalanced classification problem (the number of good loans is much larger than the number of at-risk loans).
The imbalanced-learn and Scikit-learn python libraries will be used to build and evaluate models using the two following techniques:

1. [Resampling](#Resampling)
2. [Ensemble Learning](#Ensemble-Learning)

- - -

## Files

[Resampling Starter Notebook](src/credit_risk_resampling.ipynb)

[Ensemble Starter Notebook](src/credit_risk_ensemble.ipynb)

[Lending Club Loans Data](src/Resources/LoanStats_2019Q1.csv.zip)

- - -

## Summary of Findings

### Resampling

The [imbalanced learn](https://imbalanced-learn.readthedocs.io) library was used to resample the LendingClub data.
The raw and resampled data were used to build and evaluate logistic regression classifiers.
One model was a Simple Logistic Regression without resampling the data.
The data was oversampled using the `Naive Random Oversampler` and `SMOTE` algorithms.
The data was undersampled using the `Cluster Centroids` algorithm.
The data was oversampled and undersampled using a combination `SMOTEENN` algorithm.

Each model calculated the `balanced accuracy score`, displayed the `confusion matrix` and printed the `imbalanced classification report`.

#### Results
- Which model had the best balanced accuracy score?

SMOTEENN and Naive Random Oversampling tied for the best
balanced accuracy score: 0.9934649587814939

- Which model had the best recall score?

All models have an average recall score of 0.99

- Which model had the best geometric mean score?

All models have an average geometric mean score of 0.99

### Ensemble Learning

The [Balanced Random Forest Classifier](https://imbalanced-learn.org/stable/references/generated/imblearn.ensemble.BalancedRandomForestClassifier.html) and the [Easy Ensemble Classifier](https://imbalanced-learn.org/stable/references/generated/imblearn.ensemble.EasyEnsembleClassifier.html) models were used to predict loan risk.

Each model calculated its `balanced accuracy score`, displayed its `confusion matrix` and generated its `imbalanced classification report`.
The balanced random forest classifier also printed the feature importance sorted in descending order (most important feature to least important) along with the feature score.

#### Results

* Which model had the best balanced accuracy score?

The Easy Ensemble Classifier model had a better balanced accuracy score than the Balanced Random Forest Classifier (0.931601605553446 > 0.733829270438737)

* Which model had the best recall score?

The Easy Ensemble Classifier model had a better average recall score than the Balanced Random Forest Classifier (0.9422842197035746 > 0.8426038942167975)

* Which model had the best geometric mean score?

The Easy Ensemble Classifier model had a better average geometric mean score than the Balanced Random Forest Classifier (0.9315388910882593 > 0.7255278609078841)

* What are the top three features?

According to the Balanced Random Forest Classifier, the top three features are: ['total_rec_prncp', 'last_pymnt_amnt', 'total_pymnt']
