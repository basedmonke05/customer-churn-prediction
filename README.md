# customer-churn-prediction
# Churn Prediction Model Overview

This project focuses on creating a machine learning model capable of predicting when telecom customers are likely to stop using their services. By identifying customers at risk of leaving, the company can proactively intervene, retain their business, and minimize churn-related revenue loss.

## Key Features and Approach

The model is trained on the `Telco-Customer-Churn.csv` dataset, which contains detailed information across thousands of customers regarding their service usage and billing history. 

**Data Preprocessing:**
The data was cleaned thoroughly by handling missing information, standardizing categories, converting data types, and dropping irrelevant identifiers (like customer IDs). Categorical features were encoded and numerical features were scaled for neural network compatibility.

**Feature Engineering:**
To extract deeper business insights, several custom features were engineered:
* **Customer Lifecycle Stage:** Categorized customers based on tenure (e.g., 'New', 'Growing', 'Mature', 'Loyal').
* **Revenue per Month:** A calculated score based on customer payments and tenure.
* **Service Bundle Score:** A count of the services each customer uses to gauge engagement.
* **Risk Indicators:** Derived features such as `HighRiskContract`, `FiberOpticUser`, and `SingleCustomer`.
* **Price Sensitivity Indicators:** Identified high-monthly-spend customers.
* **Interaction Features:** Calculated metrics like the `TenureChargesRatio` to understand behavioral relationships.
* **Customer Stability Score:** A loyalty metric based on partner status, dependents, contract type, and tenure.

**Handling Class Imbalance:**
Because non-churning customers heavily outnumber churning ones, class weights were applied to ensure the model did not become biased toward the majority class.

---

## Deep Neural Network Architecture

The predictive model was built using **PyTorch** with the following architecture and parameters:
* **Structure:** Deep neural network with hidden layers utilizing `ReLU` activation.
* **Regularization:** Incorporated `BatchNorm1d` for training stability and `Dropout` layers to prevent overfitting.
* **Loss Function:** Used `BCEWithLogitsLoss` with `pos_weight` to strictly handle class imbalance.
* **Optimization:** Powered by the `Adam` optimizer alongside a `ReduceLROnPlateau` scheduler to dynamically adjust learning rates.

---

## Model Performance and Business Impact

The model was evaluated rigorously to ensure high performance on unseen data, balancing accurate predictions with real-world business needs.

**Evaluation Metrics:**
* **Precision:** Measures accuracy when predicting that a customer will leave.
* **Recall:** Measures effectiveness at identifying all actual churners.
* **F1-Score:** The harmonic mean balancing precision and recall.
* **ROC-AUC Score:** Evaluates the model's overall ability to distinguish between churners and retained customers.
* **Precision-Recall Curve:** Analyzes the trade-off between precision and recall at various thresholds.

**Financial Impact Analysis:**
Beyond standard ML metrics, a financial analysis was conducted to quantify the model's ROI:
* Factored in **Customer Lifetime Value (CLV)**, the cost of retention campaigns, and the revenue saved by successfully retaining at-risk customers.
* Accounted for the wasted cost of targeting false positives (customers not actually at risk) and the revenue lost from false negatives (missed churners).
* Optimized the prediction threshold specifically to maximize the net business benefit.

**Conclusion:**
The Churn Prediction Model provides a robust framework for identifying potential churners. By enabling proactive intervention, it delivers tangible financial benefits and significantly reduces churn-related revenue loss.
