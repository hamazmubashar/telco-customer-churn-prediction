<div align="center">

# Telco Customer Churn Prediction

**Why telecom customers leave, which of them are about to, and what to offer them instead.**

[![Python](https://img.shields.io/badge/Python-3-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)
[![XGBoost](https://img.shields.io/badge/XGBoost-189FDD?style=for-the-badge)](https://xgboost.readthedocs.io/)
[![Keras](https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=keras&logoColor=white)](https://keras.io/)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

</div>

---

## The question

Keeping a customer is cheaper than winning a new one, but only if you know who's about to leave early enough to act. Using IBM's Telco Customer Churn dataset, I looked for the patterns behind churn, compared seven models for spotting it, and turned the findings into retention ideas a business could actually try.

## What drives churn

- **Contract length matters most.** Month-to-month customers churn at 42.7%; two-year customers at 2.8%.
- **Fibre customers leave more.** 41.9% churn on fibre optic versus 19.0% on DSL, which points at service quality or price rather than the product itself.
- **Electronic-check payers are high risk**, at 45.3% churn.
- **The first year is the danger zone.** Most cancellations happen within 12 months of signing up.

## Comparing models

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |
|---|:---:|:---:|:---:|:---:|:---:|
| **Logistic Regression** | **0.804** | **0.648** | **0.575** | **0.609** | **0.836** |
| Neural network (Keras) | 0.790 | 0.619 | 0.551 | 0.583 | 0.827 |
| XGBoost (tuned) | 0.790 | 0.623 | 0.529 | 0.572 | 0.832 |
| Random Forest (tuned) | 0.789 | 0.629 | 0.503 | 0.559 | 0.835 |
| Random Forest | 0.787 | 0.621 | 0.508 | 0.559 | 0.818 |
| XGBoost | 0.771 | 0.576 | 0.527 | 0.550 | 0.811 |
| Decision Tree | 0.719 | 0.470 | 0.463 | 0.466 | 0.637 |

The simplest model won. Once the features were scaled, logistic regression beat XGBoost and a neural network on both F1 and ROC-AUC. That suggests churn here depends on a few strong, mostly linear signals, and it's a useful reminder to always run a simple baseline. It's also the easiest model to explain to a retention team.

## Cleaning the data

- `TotalCharges` looked numeric but held blank strings (`' '`) for new customers. I found them by inspecting unique values, converted them to missing, cast the column to float, and dropped those rows.
- Categorical columns were one-hot encoded.
- Numeric columns were standardised for the distance- and gradient-based models (logistic regression and the neural network).

## Retention ideas

1. **Move month-to-month customers onto contracts.** Offer a 10–15% discount for switching to a one-year plan.
2. **Look into fibre service quality.** Investigate reliability complaints and include free tech support for the first six months.
3. **Shift customers off electronic checks.** Give a small bill credit for switching to automatic bank payments.

## Run it locally

```bash
git clone https://github.com/hamazmubashar/telco-customer-churn-prediction.git
cd telco-customer-churn-prediction
pip install -r requirements.txt
jupyter notebook Telco_Customer_Churn.ipynb
```

The dataset (`WA_Fn-UseC_-Telco-Customer-Churn.csv`) is included, so the notebook runs as is.

## Tech stack

Python · pandas · NumPy · Matplotlib · Seaborn · scikit-learn · XGBoost · TensorFlow / Keras

## Author

**Hamaz Mubashar** · [LinkedIn](https://www.linkedin.com/in/hamazmubashar) · [More projects](https://github.com/hamazmubashar)

Released under the [MIT License](LICENSE).
