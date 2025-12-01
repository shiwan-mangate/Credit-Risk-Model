# LOAN-DEFAULT-PREDICTOR

💡 **Loan Default Prediction System**  
A machine learning project designed to estimate the probability of a customer defaulting on a loan based on financial behaviour, credit history, and demographic information.

---

## 🖼️ App Screenshot
![Loan Default Predictor App](https://github.com/shiwan-mangate/Credit-Risk-Model/blob/main/credit-risk-app.png)

---

## 🚀 Motivation
Banks and lending companies deal with a large number of loan applications every day. Identifying high-risk borrowers early can:

- Lower credit risk  
- Improve approval decision efficiency  
- Control non-performing assets (NPAs)  
- Strengthen portfolio quality  

This project focuses on building a prediction model that uses customer information, loan data, and historical credit activity to estimate the likelihood of default.

---

## 📂 Dataset Overview

Three datasets were combined using `cust_id` as the key.

### 1️⃣ Customer Information
Includes basic demographic and financial details:
- Age  
- Gender  
- Marital status  
- Employment status  
- Income  
- Number of dependants  
- Residence type  
- Years at current address  
- City, state, and zipcode  

---

### 2️⃣ Loan Details
Covers all loan-specific attributes:
- Loan ID  
- Loan purpose  
- Loan type  
- Sanction amount  
- Loan amount  
- Processing fee  
- GST  
- Net disbursement  
- Tenure (in months)  
- Principal outstanding  
- Bank balance at application time  
- Disbursal date  
- Installment start date  
- **Default status (Target variable)**  

---

### 3️⃣ Credit Bureau Data
Contains historical repayment and enquiry information:
- Number of open accounts  
- Number of closed accounts  
- Total loan months  
- Months delinquent  
- Total DPD  
- Number of enquiries  
- Credit utilisation ratio  

---

## ➕ Feature Engineering

A few additional features were created to capture risk behaviour more effectively:

| Feature | Description |
|--------|-------------|
| loan_to_income | Ratio of loan amount to income |
| delinquency_ratio | Percentage of months with delinquency |
| avg_dpd_per_delinquency | Average DPD per delinquent month |

---

## 🛠️ Tech Stack

- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Scikit-learn  
- Imbalanced-Learn  
- XGBoost  
- Optuna  
- Joblib  
- Streamlit  

---

## 🧹 Data Preprocessing & Cleaning

### 1️⃣ Outlier Treatment
Some loan applications had unusually high processing fees. Records where:


were removed to avoid skewness.

---

### 2️⃣ Encoding Categorical Variables
Categorical fields like loan purpose, loan type, residence type, gender, and employment status were converted into numerical form using one-hot encoding.

---

### 3️⃣ Additional Feature Construction
Several new variables were derived from existing attributes (listed above) to help the model better understand customer risk levels.

---

### 4️⃣ Handling Missing Values
- Missing entries in *Residence_type* were replaced with `"Owned"`.  
- No major missing data issues were present in other columns.

---

## 🤖 Models Trained

- Logistic Regression  
- Logistic Regression with hyperparameter search  
- XGBoost Classifier  
- Logistic Regression combined with SMOTETomek balancing and Optuna tuning (final model)

---

## 📈 Model Performance

Key evaluation metrics on the test set:

- **ROC AUC:** ~0.98  
- **Gini Coefficient:** ~0.96  
- **KS Statistic:** ~85–86  
- **Recall for Default Class:** ~0.94  

The final model was selected based on stability and its ability to detect high-risk borrowers effectively.

---

## 🌐 Streamlit App

The model is deployed as a simple web app here:

🔗 **Loan Default Predictor Web App**  
https://credit-risk-model-bn4hq2sxdvkdndfyicdkyb.streamlit.app/

---




