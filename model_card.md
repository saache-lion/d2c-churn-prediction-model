# **Model Card — Customer Churn Prediction Model**

## **Intended Use**

This model is designed to identify customers at risk of churning within the next 60 days.

The model is intended to support:

* retention prioritization,  
* campaign targeting,  
* customer-risk monitoring,  
* operational decision-making.

The model should assist business teams and should not be used as a fully automated decision system.

---

## **Data Used**

The model was trained using:

* customer profile data,  
* purchase behaviour,  
* engagement activity,  
* support-ticket behaviour,  
* return/refund patterns,  
* campaign interactions.

The provided modeling snapshot dataset was used to prevent leakage and maintain temporal consistency.

---

## **Model Approach**

Two models were evaluated:

* Logistic Regression (baseline),  
* Random Forest (advanced model).

Random Forest was selected as the final model due to stronger classification performance and improved ability to capture nonlinear behavioural patterns.

---

## **Performance**

Evaluation metrics included:

* Precision,  
* Recall,  
* F1 Score,  
* ROC AUC,  
* Confusion Matrix analysis.

Recall optimization was prioritized to reduce missed churn-risk customers.

---

## **Limitations**

Potential limitations include:

* changing customer behaviour over time,  
* incomplete behavioural signals,  
* sensitivity to data drift,  
* limited external-context information.

The model may underperform during major seasonal or operational changes.

---

## **Ethical Risks**

Potential ethical considerations include:

* over-targeting vulnerable customers,  
* excessive promotional pressure,  
* unfair retention treatment across customer groups.

The model should not be used to deny services or unfairly discriminate against customers.

---

## **Monitoring Requirements**

The model should be monitored regularly for:

* performance degradation,  
* feature drift,  
* class imbalance changes,  
* campaign effectiveness,  
* false-negative rates.

Periodic retraining is recommended.

---

## **When the Model Should Not Be Used**

The model should not be used:

* as the sole basis for major customer decisions,  
* without periodic retraining,  
* during significant business-process changes,  
* when important behavioural data is missing.

