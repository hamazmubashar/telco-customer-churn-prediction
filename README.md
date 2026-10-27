# 📊 Telco Customer Churn Prediction & Analytics

An end-to-end data science project analyzing customer attrition for a telecommunications provider. This project evaluates multiple Machine Learning models—including Logistic Regression, Random Forest, XGBoost, and a Keras Deep Neural Network—to identify high-risk churn customers and propose retention strategies.

---

## 📌 Project Overview
Customer churn is a critical business metric for telecommunications companies. Retaining existing customers is significantly cheaper than acquiring new ones. The goal of this project is to:
1. Identify key drivers of customer churn through Exploratory Data Analysis (EDA).
2. Build, tune, and evaluate multiple classification models.
3. Provide actionable business recommendations based on model insights.

---

## 🧹 Data Cleaning & Preprocessing
- **Missing Value Handling:** Discovered hidden string spaces (`' '`) in `TotalCharges` during unique value inspection. Converted them to `NaN`, cast the column to `float`, and removed missing entries.
- **Categorical Encoding:** One-Hot Encoded categorical variables for machine learning compatibility.
- **Feature Scaling:** Applied `StandardScaler` to numerical features for distance/gradient-based models (Logistic Regression & Neural Networks).

---

## 📈 Key EDA Findings
- **Contract Type:** Month-to-month contract holders have the highest churn rate (**42.7%**) compared to two-year contract holders (**2.8%**).
- **Internet Service:** Fiber optic subscribers churn significantly more (**41.9%**) than DSL users (**19.0%**).
- **Payment Method:** Electronic check users exhibit a high churn rate (**45.3%**).
- **Tenure:** Customer cancellation risk is concentrated in the early months (0–12 months).

---

## 🤖 Model Performance & Evaluation

Models were evaluated across Accuracy, Precision, Recall, F1 Score, and ROC-AUC:

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Logistic Regression** | **0.8038** | **0.6476** | **0.5749** | **0.6091** | **0.8357** |
| Neural Network (Keras) | 0.7903 | 0.6186 | 0.5508 | 0.5827 | 0.8265 |
| XGBoost (Tuned) | 0.7896 | 0.6226 | 0.5294 | 0.5723 | 0.8319 |
| Random Forest (Baseline) | 0.7868 | 0.6209 | 0.5080 | 0.5588 | 0.8181 |
| Random Forest (Tuned) | 0.7889 | 0.6288 | 0.5027 | 0.5587 | 0.8345 |
| XGBoost (Baseline) | 0.7711 | 0.5760 | 0.5267 | 0.5503 | 0.8114 |
| Decision Tree (Baseline) | 0.7186 | 0.4701 | 0.4626 | 0.4663 | 0.6366 |

> **Best Performing Model:** **Logistic Regression** achieved the highest overall **F1 Score (0.6091)** and **ROC-AUC (0.8357)**, showing that a scaled linear boundary captures the primary churn signals effectively.

---

## 💡 Business Strategy & Recommendations
1. **Contract Retention Incentives:** Offer a 10–15% bill discount to month-to-month users who transition to a 1-year contract.
2. **Fiber Optic Service Quality:** Investigate service reliability issues and bundle free tech support for the first 6 months.
3. **Auto-Pay Migration:** Encourage electronic check users to switch to automatic bank transfers with small billing credits.

---

## 🛠️ Tech Stack & Libraries
- **Language:** Python
- **Data Manipulation:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Machine Learning:** Scikit-Learn, XGBoost
- **Deep Learning:** Keras / TensorFlow

---

## ▶️ Run It Locally

```bash
git clone https://github.com/hamazmubashar/telco-customer-churn-prediction.git
cd telco-customer-churn-prediction
pip install -r requirements.txt
jupyter notebook Telco_Customer_Churn.ipynb
```

The dataset (`WA_Fn-UseC_-Telco-Customer-Churn.csv`, IBM Telco Customer Churn sample) is included in the repo.

---

## 👤 Author

**Hamaz Mubashar** · [LinkedIn](https://www.linkedin.com/in/hamazmubashar) · [More projects](https://github.com/hamazmubashar)

Licensed under the [MIT License](LICENSE).
