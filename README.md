# Credit Card Fraud Detection (2026 Dataset)

This project builds a Machine Learning model using **Logistic Regression** to detect fraudulent credit card transactions. The dataset includes traditional transaction features alongside modern risk signals like VPN usage, device type, IP/country mismatches, and AI-generated scam flags.

---

## 📌 Features

- **Dataset Size:** 20,000 records, 26 original features.
- **Data Preprocessing:** 
  - Missing value and duplicate verification.
  - One-hot encoding for categorical variables (merchant category, card type, channel, device type, risk flags, etc.).
- **Model Training:** 
  - Logistic Regression with class-weight balancing (`class_weight="balanced"`) to handle class imbalance.
  - Stratified 80/20 train-test split.

---

## 🛠 Tech Stack

- **Language:** Python 3.x
- **Libraries Used:**
  - `pandas` - Data manipulation & analysis.
  - `scikit-learn` - Machine learning model and evaluation metrics.

---

## 📂 Dataset Overview

The dataset (`credit_card_fraud_2026.csv`) includes features such as:
- **Transaction Details:** `amount_usd`, `hours_since_last_txn`, `txn_count_last_24h`, `time_of_day_hour`, `day_of_week`
- **Card & User Info:** `card_type`, `card_age_months`, `customer_age`, `account_balance_usd`, `distance_from_home_km`
- **Risk & Security Signals:** `auth_method`, `used_vpn`, `ip_country_mismatch`, `billing_shipping_mismatch`, `cvv_retry_count`, `velocity_score`, `is_ai_generated_scam_attempt`, `merchant_risk_score`.
- **Target Variable:** `is_fraud` (0 = Normal, 1 = Fraudulent).

---

## 📊 Model Evaluation & Results

The Logistic Regression model was evaluated on a test set of 4,000 transactions:

### 📈 Metrics Overview
- **Accuracy:** 85.42%.
- **Recall (Sensitivity):** 88.24% (Catches 60 out of 68 actual fraud cases).
- **Precision:** 9.45% (0.09).
- **F1-Score:** 17.07% (0.17).

---

### 🧩 Confusion Matrix
```text
              Predicted Normal (0)   Predicted Fraud (1)
Actual Normal (0)      3357                    575
Actual Fraud  (1)         8                     60
```[cite: 1]

---

### 📋 Classification Report

```text
              precision    recall  f1-score   support

           0       1.00      0.85      0.92      3932
           1       0.09      0.88      0.17        68

    accuracy                           0.85      4000
   macro avg       0.55      0.87      0.55      4000
weighted avg       0.98      0.85      0.91      4000
```[cite: 1]

---

### 💡 Performance Analysis

- **High Fraud Recall (88.24%):** By setting `class_weight="balanced"`, the model prioritizes catching fraudulent transactions (60 detected, 8 missed).
- **Trade-off (Precision vs Recall):** Because the model is heavily weighted toward finding fraud, it produces 575 false positives (normal transactions flagged as fraud), resulting in a precision of 9.45%[cite: 1]. In financial security contexts, high recall is typically prioritized over precision to avoid costly missed fraud.

---



```

2. **Install Required Libraries:**
```bash
pip install pandas scikit-learn

```


3. **Ensure Dataset Placement:**
Place `credit_card_fraud_2026.csv` in the root directory alongside your script or notebook.


4. **Run the Notebook:**
```bash
jupyter notebook

```



```

```
