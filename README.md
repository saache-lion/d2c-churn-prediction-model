# **Customer Churn Prediction Model**

## **Project Overview**

This project focuses on building a machine-learning model to predict customer churn within the next 60 days for a D2C business.

The objective is to help the company:

* identify high-risk customers early,  
* improve retention decision-making,  
* optimize retention campaigns,  
* reduce customer attrition,  
* improve customer lifetime value.

The project uses behavioural, transactional, engagement, and support-interaction data available on or before the customer snapshot date.

---

# **Objective**

The primary objective of this project is to:

* build a churn-prediction model,  
* compare baseline and advanced machine-learning models,  
* evaluate classification performance,  
* interpret prediction drivers,  
* support business retention strategies.

---

# **Dataset Used**

The project uses:

| Dataset | Description |
| ----- | ----- |
| rfm\_modeling\_snapshot.csv | Customer-level behavioural and churn modeling dataset |

The dataset includes:

* customer profile variables,  
* RFM behavioural metrics,  
* support-ticket behaviour,  
* return/refund behaviour,  
* web/app engagement activity,  
* campaign interaction metrics,  
* churn labels.

---

# **Leakage Prevention**

Strict leakage prevention practices were followed during model development.

Only variables available on or before the customer snapshot date were used as input features.

The target variable:

* `churn_next_60d`

represents future churn behaviour and was never used during feature generation.

Future activity, post-churn behaviour, and post-snapshot interventions were excluded from model inputs.

The provided dataset split:

* train,  
* validation,  
* test,

was preserved to maintain temporal consistency and evaluation integrity.

---

# **Models Trained**

## **1\. Logistic Regression (Baseline)**

A Logistic Regression model was used as the baseline classifier because:

* it is interpretable,  
* computationally efficient,  
* suitable for binary classification problems.

---

## **2\. Random Forest (Advanced Model)**

A Random Forest classifier was used as the advanced model because:

* it captures nonlinear relationships,  
* handles behavioural complexity effectively,  
* provides feature-importance analysis,  
* is robust to noise and outliers.

---

# **Evaluation Metrics**

The following evaluation metrics were used:

* Accuracy  
* Precision  
* Recall  
* F1 Score  
* ROC AUC Score  
* Confusion Matrix

Accuracy alone was not considered sufficient because churn prediction is an imbalanced classification problem.

Recall optimization was prioritized to reduce missed churn-risk customers.

---

# **Threshold Selection Strategy**

A custom probability threshold of:

* `0.40`

was selected instead of the default 0.50 threshold.

## **Business Rationale**

The business cost of missing a true churn-risk customer is typically higher than targeting a customer who would not churn.

Using a lower threshold helps:

* improve recall,  
* identify more at-risk customers,  
* increase retention opportunity coverage.

The threshold can later be adjusted based on:

* campaign budget,  
* operational capacity,  
* customer lifetime value.

---

# **Feature Importance**

Important predictive features included:

* recency,  
* purchase frequency,  
* monetary value,  
* support-ticket activity,  
* return rates,  
* engagement sessions,  
* abandoned carts,  
* campaign interactions.

These features helped the model identify:

* disengaged customers,  
* dissatisfied customers,  
* declining purchase behaviour,  
* operational-risk customers.

---

# **Error Analysis**

Error analysis was conducted using:

* false positives,  
* false negatives.

## **False Positives**

Customers predicted to churn who ultimately remained active.

Potential causes:

* temporary inactivity,  
* seasonal purchasing behaviour,  
* conservative threshold strategy.

## **False Negatives**

Customers who churned but were not identified by the model.

Potential causes:

* sudden behavioural changes,  
* external operational factors,  
* unobserved customer dissatisfaction.

Special attention was given to high-value false negatives due to their business impact.

---

# **Model Card Summary**

The project includes a detailed model card covering:

* intended use,  
* dataset description,  
* modeling approach,  
* performance,  
* limitations,  
* ethical considerations,  
* monitoring requirements,  
* operational constraints.

---

# **Files Included**

| File | Purpose |
| ----- | ----- |
| 01\_churn\_modeling.ipynb | Main churn-modeling notebook |
| predictions.csv | Customer-level prediction outputs |
| feature\_importance.csv | Model feature importance results |
| model\_card.md | Responsible-AI and model documentation |
| error\_analysis.md | Prediction error analysis |
| threshold\_selection.md | Business threshold justification |
| requirements.txt | Project dependencies |
| README.md | Project documentation |

---

# **Technologies Used**

* Python  
* Pandas  
* NumPy  
* Matplotlib  
* Seaborn  
* Scikit-learn  
* Jupyter Notebook

---

# **Project Structure**

part\_3\_churn\_prediction/  
│  
├── data/  
├── notebooks/  
│   └── 01\_churn\_modeling.ipynb  
│  
├── reports/  
│   ├── model\_card.md  
│   ├── error\_analysis.md  
│   └── threshold\_selection.md  
│  
├── outputs/  
│   ├── predictions.csv  
│   ├── feature\_importance.csv  
│   └── confusion\_matrix.png  
│  
├── requirements.txt  
└── README.md

---

# **How to Run**

## **Install Dependencies**

pip install \-r requirements.txt

## **Launch Notebook**

jupyter notebook

Open:

01\_churn\_modeling.ipynb

---

# **Business Goal**

The ultimate goal of this project is to help the company:

* proactively identify churn-risk customers,  
* improve retention efficiency,  
* optimize campaign targeting,  
* reduce revenue loss from churn,  
* support data-driven retention strategies.

The project demonstrates how behavioural analytics and machine learning can be combined to improve customer-retention decision-making.
