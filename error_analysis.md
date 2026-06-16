# **Error Analysis Report**

## **Objective**

The purpose of this analysis is to understand where the churn-prediction model performs well and where prediction errors occur.

Special attention was given to:

* false positives,  
* false negatives,  
* customer behavioural patterns,  
* operational implications of prediction errors.

Understanding model errors is important because churn prediction directly influences retention spending and customer outreach decisions.

---

# **Prediction Error Types**

## **1\. False Positives**

False positives occur when:

* the model predicts a customer will churn,  
* but the customer actually remains active.

### **Business Impact**

False positives may lead to:

* unnecessary retention campaigns,  
* excess promotional spending,  
* operational inefficiencies.

However, false positives are generally considered less harmful than false negatives because retention outreach may still strengthen customer relationships.

---

## **2\. False Negatives**

False negatives occur when:

* the model predicts a customer will remain active,  
* but the customer actually churns.

### **Business Impact**

False negatives are especially costly because:

* high-risk customers are missed,  
* retention opportunities are lost,  
* customer attrition increases,  
* revenue may decline.

Reducing false negatives is particularly important for high-value customers.

---

# **Common Error Patterns Observed**

## **False Positive Patterns**

Several false-positive customers displayed:

* temporary engagement decline,  
* seasonal inactivity,  
* low recent sessions,  
* reduced purchasing frequency without actual churn.

These customers may have resumed activity naturally after the prediction window.

---

## **False Negative Patterns**

Several false-negative customers demonstrated:

* sudden behavioural changes,  
* abrupt engagement drop,  
* unexpected operational dissatisfaction,  
* hidden churn drivers not fully captured in the dataset.

Some customers churned despite previously stable purchasing behaviour.

---

# **Manual Customer-Level Error Review**

| Customer ID | Actual Churn | Predicted | Observation | Interpretation |
| ----- | ----- | ----- | ----- | ----- |
| CUST00405 | 1 | 0 | Moderate purchase activity but high return rate | Model underestimated dissatisfaction signals |
| CUST01333 | 1 | 0 | Low engagement and low sessions before churn | Engagement decline may not have crossed threshold strongly enough |
| CUST00565 | 0 | 1 | Reduced purchase frequency but stable engagement | Model treated temporary inactivity as churn risk |
| CUST01974 | 0 | 1 | Support complaints present but customer retained | Complaint activity alone did not lead to churn |
| CUST01048 | 1 | 0 | Historically valuable customer became inactive suddenly | Sudden churn behaviour difficult to capture |
| CUST02131 | 0 | 1 | Low browsing sessions despite strong purchase value | Transaction-driven customer behaviour confused the model |
| CUST01344 | 1 | 1 | Extremely low activity and zero purchases | Correctly identified as high-risk churn customer |
| CUST01208 | 0 | 1 | Low engagement but stable purchase behaviour | Customer remained loyal despite low browsing activity |
| CUST00798 | 0 | 0 | Strong monetary and frequency signals | Correctly classified as retained customer |
| CUST01317 | 1 | 1 | Completely inactive customer profile | Correctly identified as churn-risk customer |

---

# **Key Findings**

Several important findings emerged during error analysis:

* Low engagement activity is a strong churn indicator but may occasionally create false positives.  
* High-value customers may churn unexpectedly despite historically stable behaviour.  
* Support complaints and return rates improve churn detection but are not perfect standalone predictors.  
* Certain customers exhibit transaction-driven behaviour with minimal browsing activity, which may confuse engagement-based models.  
* The selected threshold improves recall but increases some unnecessary retention targeting.

---

# **Business Recommendations**

Based on error analysis, the following improvements are recommended:

## **Improve Behavioural Monitoring**

Include:

* session trends,  
* engagement velocity,  
* purchase timing changes,  
* support sentiment analysis.

## **Introduce Customer Lifetime Value Weighting**

False negatives involving high-value customers should receive greater modeling attention.

## **Dynamic Threshold Optimization**

Thresholds may be adjusted based on:

* campaign budget,  
* customer segment,  
* operational capacity.

## **Add Temporal Trend Features**

Trend-based behavioural features may help identify sudden disengagement patterns earlier.

---

# **Overall Conclusion**

The model demonstrates strong capability in identifying many churn-risk customers while maintaining interpretable business behaviour patterns.

However:

* churn behaviour remains partially unpredictable,  
* customer intent can change rapidly,  
* operational dissatisfaction may not always appear directly in behavioural metrics.

Continuous monitoring, retraining, and error analysis are necessary to maintain reliable churn-prediction performance over time.

