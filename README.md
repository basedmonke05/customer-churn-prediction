# customer-churn-prediction
Churn Prediction Model Overview

This project is about creating a learning model that can predict when customers of a telecom company are likely to stop using their services. We want to find out which customers are at risk of leaving so we can try to keep them. The goal is to minimize the amount of money the company loses when customers leave.

Key Features and Approach:

The model is trained on a dataset called Telco-Customer-Churn.csv. This dataset has a lot of information about thousands of customers including information the services they use and how much they pay.

We cleaned the data thoroughly. This included dealing with missing information making sure categories were standardized and converting data types. We also removed customer IDs.

We also created features that give us insights into the business. These include:

* Customer Lifecycle Stage: We categorized customers based on how they have been with the company, such as 'New' 'Growing' 'Mature' or 'Loyal'.

* Revenue per Month: We calculated a score based on how much each customer pays and how long they have been with the company.

* Service Bundle Score: We counted how services each customer uses to see how engaged they are.

* Risk Indicators: We created features like HighRiskContract, FiberOpticUser and SingleCustomer based on what we learned from exploring the data.

* Price Sensitivity Indicators: We identified customers who spend a lot of money each month.

* Interaction Features: We calculated ratios like TenureChargesRatio to understand how different aspects of customer behavior are related.

* Customer Stability Score: We created a score that shows how loyal each customer is based on their partner status, dependents, contract type and how long they have been with the company.

We scaled features and encoded categorical features so they could be used in the neural network.

We also dealt with the fact that the data is imbalanced. There are customers who do not leave than customers who do. We used class weights to make sure the model does not get too good at predicting the majority class.

Deep Neural Network Architecture:

We built a neural network using PyTorch. The network has hidden layers and uses ReLU activation. It also has BatchNorm1d for training and Dropout layers to prevent overfitting. We used BCEWithLogitsLoss with pos_weight to handle class imbalance and Adam optimizer with ReduceLROnPlateau scheduler for learning rates.

Model Performance and Business Impact:

The model performed well on data.

We measured Precision, which shows how accurate the model is when it predicts that a customer will leave.

We measured Recall, which shows how good the model is at identifying all customers who actually leave.

We measured F1-Score, which's a combination of precision and recall.

We also measured ROC AUC Score, which shows how well the model can distinguish between customers who leave and customers who do not.

We looked at the Precision-Recall Curve, which helps us understand the trade-off between precision and recall.

We did a financial analysis to see how much money the model can save the company.

We considered Customer Lifetime Value, the cost of trying to keep customers and the revenue saved from identifying customers who are at risk of leaving.

We also considered the wasted cost of trying to keep customers who're not at risk of leaving and the revenue lost from customers who leave.

We calculated the benefit and return on investment.

We optimized the prediction threshold to maximize the business benefit.

This model is a way to identify customers who are at risk of leaving. It can help the company keep customers and reduce the amount of money lost when customers leave. The Churn Prediction Model provides a framework, for identifying potential churners enabling proactive intervention and delivering tangible financial benefits by significantly reducing churn-related revenue loss. The telecom company can use the Churn Prediction Model to minimize revenue loss and keep customers.
