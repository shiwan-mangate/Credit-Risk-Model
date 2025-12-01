LOAN-DEFAULT-PREDICTOR

💡 Loan Default Prediction System
Predicting the probability of a customer defaulting on a loan using advanced machine learning and financial risk features.

----
🖼️ App Screenshot

(Add Streamlit / Web App screenshot here)

----

🚀 Motivation
Loan defaults significantly impact financial institutions and lending platforms. Accurate early prediction helps in:
Reducing credit risk
Improving loan approval decisions
Reducing NPAs
Enhancing portfolio quality
This model leverages demographics, loan details, and credit bureau history to predict the likelihood of default using machine learning, minimizing manual evaluation errors.
-----

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

3. Loan Details
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

----
➕ Engineered Features
Feature Name	Description
loan_to_income	Captures repayment burden relative to income
delinquency_ratio	% of months where customer was delinquent
avg_dpd_per_delinquency	Average DPD per delinquent month

----
🛠️ Tech Stack & Tools
Python
NumPy, Pandas
Matplotlib, Seaborn
Scikit-learn
Imbalanced-Learn (SMOTETomek)
XGBoost
Optuna
Joblib
Streamlit 

-----
Data Preprocessing & Feature Engineering
1. Handling Outliers
Outliers in financial variables can mislead the model.

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
loan_purpose_encoded	Encoded loan purpose values
residence_type_encoded	Encoded residence type values
These features significantly improved model performance and credit-risk interpretability.

4. Missing Value Treatment
Residence_type missing values were filled with mode: "Owned"
No significant missing values in other fields

----
🤖 Models Tried
Logistic Regression (Baseline)
Logistic Regression + RandomizedSearchCV
XGBoost Classifier
Logistic Regression + SMOTETomek + Optuna (Final Model)

----
📈 Results – High Performance Metrics
ROC AUC: ~0.98
Gini Coefficient: ~0.96
KS Statistic: ~85–86 (Excellent)
Recall for Default Class: ~0.94
The model is optimized to detect high-risk borrowers with strong discrimination capability

----
🌐 Streamlit App
(Add your deployed app link here)
🔗 Loan Default Predictor Web App
