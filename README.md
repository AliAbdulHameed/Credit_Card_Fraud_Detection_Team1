# Credit Card Fraud Detection — Team 1

This project focuses on identifying fraudulent credit card transactions using machine learning. Fraud cases are extremely rare compared to legitimate activity, so the main challenge is detecting fraud effectively while keeping financial losses low when errors occur.

---

## Dataset

We used the Credit Card Fraud Detection dataset from Kaggle:

Source: https://www.kaggle.com/mlg-ulb/creditcardfraud

The dataset contains:

- 284,807 credit card transactions
- 492 fraud cases (approximately 0.17%)
- PCA-transformed numerical features (V1–V28) for privacy protection
- Amount and Time preserved as original features
- Class as the target label (0 = legitimate, 1 = fraud)

---

## Data Preparation

Steps performed:

- Verified class imbalance
- Removed duplicate records
- Standardized Time and Amount features using StandardScaler
- Stratified train-test split (85% training / 15% testing)

---

## Models Tested

We trained and evaluated three machine learning models:

- Logistic Regression
- Random Forest Classifier
- XGBoost Classifier

Each model was run twice:

1. Baseline (no class imbalance handling)
2. SMOTE oversampling applied to the training data

---

## Evaluation Metrics

We compared performance using:

- Precision
- Recall
- F1-Score
- ROC-AUC

These metrics measure both fraud detection success and the risk of false alarms.

---

## Cost-Based Evaluation

Since real-world mistakes have different financial outcomes, we added a cost metric.

| Error Type | Description | Cost Impact |
|-----------|-------------|-------------|
| False Negative | Fraud missed | Full transaction amount lost |
| False Positive | Legitimate flagged as fraud | $25 investigation cost |

Total Cost = Missed Fraud Loss + Investigation Cost

This approach ranks models by financial effectiveness instead of only technical accuracy.

---

## Results Overview

- SMOTE improved recall and fraud capture rate
- Random Forest and XGBoost outperformed Logistic Regression
- Best overall model was the one with the lowest total financial loss

---

## Tools Used

- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- XGBoost
- Imbalanced-Learn (SMOTE)
- Google Colab

---

## Team Members

- Ali Abdul-Hameed
- James Harvey
- Tushar Kumar
