LOAN-DEFAULT-PREDICTOR

💡 Loan Default Prediction System
Predicting the probability of a customer defaulting on a loan using advanced machine learning and financial risk features.

🖼️ App Screenshot

(Add Streamlit / Web App screenshot here)

🚀 Motivation

Loan defaults significantly impact financial institutions and lending platforms.
Accurate early prediction helps in:

Reducing credit risk

Improving loan approval decisions

Reducing NPAs

Enhancing portfolio quality

This model leverages demographics, loan details, and credit bureau history to predict the likelihood of default using machine learning, minimizing manual evaluation errors.

📂 Dataset Information

The project uses three structured datasets merged through cust_id:

1. Customer Information

Age

Gender

Marital_status

Employment_status

Income

Number_of_dependants

Residence_type

Years_at_current_address

Location (City, State, Zipcode)

2. Loan Details

Loan_id

Loan_purpose

Loan_type

Sanction_amount

Loan_amount

Processing_fee

GST

Net_disbursement

Loan_tenure_months

Principal_outstanding

Bank_balance_at_application

Disbursal_date

Installment_start_dt

Default (Target Variable)

3. Credit Bureau Data

Number_of_open_accounts

Number_of_closed_accounts

Total_loan_months

Delinquent_months

Total_dpd

Enquiry_count

Credit_utilization_ratio

➕ Engineered Features

To enhance predictive power, the following features were created:

Feature Name	Description
loan_to_income	Captures repayment burden relative to income.
delinquency_ratio	% of months where customer was delinquent.
avg_dpd_per_delinquency	Average DPD per delinquent month.
🛠️ Tech Stack & Tools

Python

NumPy, Pandas

Matplotlib, Seaborn

Scikit-learn

Imbalanced-Learn (SMOTETomek)

XGBoost

Optuna

Joblib

Streamlit (optional for UI)

🧹 Data Preprocessing & Feature Engineering

A robust preprocessing pipeline was designed to clean, transform, and prepare the dataset for ML modeling.

✅ Key Steps in Preprocessing
1. Handling Outliers

Outliers in financial variables can mislead the model.

Example:
Processing Fee vs Loan Amount Ratio
Values above 3% were removed:

df = df[(df['processing_fee'] / df['loan_amount']) < 0.03]

2. Encoding Categorical Features

One-hot encoding was applied to:

Loan_purpose

Loan_type

Residence_type

Gender

Employment_status

3. Feature Engineering
Feature Name	Description
loan_to_income	Loan amount ÷ customer income
delinquency_ratio	(Delinquent months ÷ total loan months) * 100
avg_dpd_per_delinquency	Total DPD ÷ delinquent months
loan_purpose_encoded	Encoded premium loan purpose types
residence_type_encoded	Numerical representation for ML

These features significantly improved model performance and credit-risk interpretability.

4. Missing Value Treatment

Residence_type missing values filled with mode: "Owned"

No significant missing values in other fields

5. Feature Scaling

MinMax scaling applied to numerical variables:

scaler = MinMaxScaler()
X[cols_to_scale] = scaler.fit_transform(X[cols_to_scale])

🤖 Models Tried

Logistic Regression (Baseline)

Logistic Regression + RandomizedSearchCV

XGBoost Classifier

Logistic Regression + SMOTETomek + Optuna (Final Model)

✅ Final Model: Logistic Regression (Optimized with Optuna)

After balancing the dataset using SMOTETomek, Optuna performed hyperparameter tuning.

Best Parameters:

{
    'C': 1259.05,
    'solver': 'newton-cg',
    'tol': 0.0001239,
    'class_weight': None
}


This model achieved the best balance between:

Recall for default class

AUC

Gini

KS statistic

Out-of-sample stability

📈 Results
✔ High Performance Metrics

ROC AUC: ~0.98

Gini Coefficient: ~0.96

KS Statistic: ~85–86 (Excellent)

Recall for Default Class: ~0.94

The model is optimized to detect high-risk borrowers with strong discrimination capability.

💾 Saved Model Artifact

The final model is saved as:

ARTIFACTS/model_data.joblib


This file includes:

Trained Logistic Regression model

Feature list

Scaler

Columns requiring scaling

🌐 Streamlit App

(Add your deployed app link here)
🔗 Loan Default Predictor Web App

🖼️ App Screenshot

(Insert Streamlit UI screenshot)

🧠 Professional Use Case

This ML system can be deployed in:

🏦 Bank Loan Origination Systems
📊 Credit Risk Assessment Dashboards
📈 Portfolio Monitoring Tools
👥 FinTech Loan Approval Engines
🧮 NBFC / Microfinance credit evaluation

🚧 Future Improvements

Add SHAP-based model explainability

Train on larger & cross-institution datasets

Deploy via FastAPI

Add customer-level dashboards

Introduce scorecards (PD mapping)

👨‍💻 Author

Shiwan Mangate
B.Tech in Artificial Intelligence
NIT Rourkela
