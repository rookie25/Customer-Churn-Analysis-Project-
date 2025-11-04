# 📊 Customer Churn Analysis Project  

### 🎯 Project Objective  
The goal of this project is to analyze customer churn behavior for a telecom subscription business and build a predictive model that identifies which customers are most likely to discontinue their service.  
This end-to-end workflow demonstrates practical data analytics, machine learning, and business insight skills — from exploration to actionable recommendations.

---

### 🧠 Business Context  
Customer churn is one of the biggest challenges for subscription-based businesses.  
Acquiring a new customer is up to **5× more expensive** than retaining an existing one.  
By predicting which customers are likely to leave, companies can take proactive actions to improve retention and reduce revenue loss.

---

### 🧩 Dataset  
**Source:** IBM Telco Customer Churn (Kaggle)  
- **Rows:** 7,043 customers  
- **Target column:** `Churn` (Yes/No)  
- **Key fields:** Tenure, MonthlyCharges, TotalCharges, Contract Type, Internet/Phone Services, Payment Method  

---

### ⚙️ Methodology  

1. **Data Exploration**
   - Examined data types, missing values, and churn distribution.  
   - Visualized churn patterns by tenure, contract, and monthly charges.  

2. **Data Cleaning & Feature Engineering**
   - Fixed missing values in `TotalCharges`.  
   - Created derived features:  
     - `revenue_per_month` = TotalCharges ÷ Tenure  
     - `service_count` = number of active services  
     - `has_streaming` = 1 if customer uses streaming services  
     - `tenure_segment` = grouped tenure buckets (0–1 yr, 1–2 yr, 2–4 yr, 4+ yr)  
   - Added numeric churn flag (`churn_flag` = 1 if churned, else 0).

3. **Customer Segmentation**
   - Used **K-Means clustering** on tenure, monthly charges, and service count.  
   - Identified four distinct customer segments with different churn and spending behavior.

4. **Predictive Modeling**
   - Models: **Logistic Regression** and **Random Forest**  
   - Achieved **~79% accuracy** and **AUC ≈ 0.83**.  
   - Evaluated using precision, recall, F1-score, and ROC-AUC.

5. **Feature Importance**
   - Top churn drivers:  
     `TotalCharges`, `revenue_per_month`, `MonthlyCharges`, `tenure`, `Contract`, `OnlineSecurity`, `TechSupport`

6. **Business Insights & Recommendations**
   - Derived actionable insights for retention strategies (below).

---

### 📈 Key Results  

| Model | Accuracy | AUC | Comments |
|--------|-----------|------|-----------|
| **Logistic Regression** | 79.4% | 0.839 | Interpretable baseline model |
| **Random Forest** | 79.1% | 0.828 | Slightly lower AUC but captures nonlinear patterns |

---

### 💡 Business Insights  

1. **High-Risk Group (≈ 26% of customers)**  
   - Short-tenure, month-to-month users with higher monthly charges churn most.  
   - Focus retention efforts on this early-stage group.

2. **Loyal Customers**  
   - Long-term subscribers on 1- or 2-year contracts have < 10% churn.  
   - Maintain satisfaction through loyalty programs and upsell opportunities.

3. **Key Churn Drivers**
   - High `MonthlyCharges` → possible price sensitivity.  
   - Lack of `OnlineSecurity` or `TechSupport` → low engagement.  
   - Short `tenure` and flexible contracts → low commitment.  

4. **Recommendations**
   - Offer **contract incentives** for multi-year subscriptions.  
   - **Bundle value-added services** (security, tech support) to improve stickiness.  
   - Launch **early-tenure engagement programs** within the first 3 months.  
   - **Automate payments** to reduce involuntary churn due to billing issues.

---

### 🧰 Tech Stack  
- **Python:** pandas, numpy, matplotlib, seaborn, scikit-learn  
- **Visualization:** Power BI (for dashboard)  
- **Environment:** Jupyter Notebook  
- **Version Control:** GitHub  

---
