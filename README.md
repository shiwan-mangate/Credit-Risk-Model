
---

### 2️⃣ Encoding Categorical Features
One-hot encoding was applied to:

- Loan_purpose  
- Loan_type  
- Residence_type  
- Gender  
- Employment_status  

---

### 3️⃣ Feature Engineering

| Feature Name               | Description |
|----------------------------|-------------|
| loan_to_income            | Loan amount ÷ customer income |
| delinquency_ratio         | (Delinquent months ÷ total loan months) × 100 |
| avg_dpd_per_delinquency   | Total DPD ÷ delinquent months |
| loan_purpose_encoded      | Encoded loan purpose values |
| residence_type_encoded    | Encoded residence type values |

These features significantly improved model performance and credit-risk interpretability.

---

### 4️⃣ Missing Value Treatment
- Missing `Residence_type` values filled with: `"Owned"`  
- No major missing values in other fields  

---

## 🤖 Models Tried
- Logistic Regression (Baseline)  
- Logistic Regression + RandomizedSearchCV  
- XGBoost Classifier  
- **Logistic Regression + SMOTETomek + Optuna (Final Model)**  

---

## 📈 Results – High Performance Metrics
- **ROC AUC:** ~0.98  
- **Gini Coefficient:** ~0.96  
- **KS Statistic:** ~85–86 *(Excellent)*  
- **Recall for Default Class:** ~0.94  

The model is optimized to detect **high-risk borrowers** with strong discrimination capability.

---

## 🌐 Streamlit App
Try the live application here:

🔗 **Loan Default Predictor Web App**  
👉 https://credit-risk-model-bn4hq2sxdvkdndfyicdkyb.streamlit.app/

---


