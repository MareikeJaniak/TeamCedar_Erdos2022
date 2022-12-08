# TeamCedar_Erdos2022
final project from Team Cedar for the Erdos Institute Bootcamp 2022

### Project Description and Goals

Our project focused on analyzing a dataset of claim billing data for prescription medications. 

The goals for our project were twofold:

1) Predict whether a prescription medication request would be accepted or rejected by insurance.
2) If accepted, predict the amount of money the patient will likely be required to pay for the prescription.

Stakeholders for this project include CoverMyMeds, as well as patients and clinicians. By being able to know whether a medication is likely to be accepted and how much the patient will have to pay, medical professionals can make informed decisions at the point of prescription, especially when multiple medications may be available. 

### Dataset

The data are from a simulated dataset provided by CoverMyMeds. We have 9 features and close to 14 million observations. 

The columns include:
* tx_date – The date on which the pharmacy transaction was attempted
* pharmacy – The particular pharmacy where the transaction was attempted
* diagnosis – The diagnosis of the patient associated with the transaction
* drug – The drug that the patient was prescribed that the pharmacy is attempting to bill
* bin – The broadest identifier of a patient’s insurance plan (banking identification number)
* pcn – An identifier that more narrowly specifies a plan underneath the broader “bin”
* group – Another identifier that more narrowly specifies a plan underneath the broader “bin”
* rejected – Whether the billing transaction was rejected by the plan
* patient_pay – The amount of copayment for which the patient is responsible

### Exploratory Data Analysis

The CoverMyMeds dataset includes close to 14 million observations of (simulated) claim billing data for prescription medications, including whether the claim was accepted or rejected, and how much the patient paid as a co-pay for the prescription. We explore the dataset in detail with visualizations and descriptive statistics in the jupyter notebook [data_exploration_TeamCedar.ipynb](https://github.com/MareikeJaniak/TeamCedar_Erdos2022/blob/70c4e53e819df312f7c8578a277ce516ffaf1182/data_exploration_TeamCedar.ipynb). Below we show a brief overview of the most relevant findings from our data exploration. 

The dataset is quite imbalanced when it comes to acceptance and rejection rates. Luckily for patients, most claims for prescriptions are accepted:

![Screen Shot 2022-12-07 at 11 38 13 AM](https://user-images.githubusercontent.com/30602072/206237666-28babee1-cdbe-4d74-b182-5c3c62c4402b.png)

This is especially true for generic medications, of which over 99% are accepted, while acceptance rates for branded medications are lower:

![Screen Shot 2022-12-07 at 11 38 24 AM](https://user-images.githubusercontent.com/30602072/206237601-91cad3c6-7ff0-41dc-a8f3-9e5231f5b673.png)

A discrepancy between branded and generic medications is also apparent when considering patient co-pays. Branded medications have a higher average cost to the patient:

![Screen Shot 2022-12-07 at 11 31 58 AM](https://user-images.githubusercontent.com/30602072/206236166-b154653d-5852-4725-8300-c11d4bfb44f4.png)

### Goal 1: Predicting likelihood of acceptance/rejection

Details for the model run for goal 1 are in the jupyter notebook titled [Goal1_classifier_TeamCedar.ipybnb](https://github.com/MareikeJaniak/TeamCedar_Erdos2022/blob/d9e685a8f80e8f92484632150767bb58f2471908/Goal1_classifier_TeamCedar.ipynb)

We used the XGBClassifier from xgboost to predict whether a medication will be accepted or rejected by insurance. Our model did not perform very well at the default 0.5 threshold. We, therefore, explored other thresholds that would minimize false negatives, as these are what would be most costly for the patients. We decided on a threshold of 0.17 as the optimal trade-off between specificity and recall. 

![Screen Shot 2022-12-07 at 5 00 58 PM](https://user-images.githubusercontent.com/30602072/206326489-558fb19e-cc1e-4655-9716-939c5c291d02.png)
![Screen Shot 2022-12-07 at 5 11 56 PM](https://user-images.githubusercontent.com/30602072/206326507-f87010df-a59e-4092-b968-424b4e03b18a.png)
![Screen Shot 2022-12-07 at 4 56 56 PM](https://user-images.githubusercontent.com/30602072/206326523-e1f1901c-29f7-4901-ad0f-dfe7e1287e09.png)

### Goal 2: Predicting required patient pay

Details for the model run for goal 2 are in the jupyter notebook titled [Goal2_regression_model_TeamCedar.ipynb](https://github.com/MareikeJaniak/TeamCedar_Erdos2022/blob/46561d1d929cb6f052b16678b51433d031e1bad0/Goal2_regression_model_TeamCedar.ipynb)

We used the XGBRegressor model from xgboost to predict how much patients will have to pay for their medications. Our model performed well and predicted co-pay accurately to within a little over $1 on average. 

![Screen Shot 2022-12-07 at 5 10 24 PM](https://user-images.githubusercontent.com/30602072/206325443-0c6c5a39-1fa5-4c59-883c-2ee435775de0.png)

Mean patient pay: $26.10
Baseline mean absolute error: $21.80
Model mean absolute error: $1.17

### Conclusions and Future Directions

#### Future steps
Build a tool that allows providers to see 
* likelihood of acceptance/rejection
* cost of the medication to the patient
* potential alternative prescriptions for the diagnosis with better odds of being accepted and/or a lower cost to the patient
