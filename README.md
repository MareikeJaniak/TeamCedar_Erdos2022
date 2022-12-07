# TeamCedar_Erdos2022
final project from Team Cedar for the Erdos Institute Bootcamp 2022

### Project Description and Goals

Our project focused on analyzing a dataset of claim billing data for prescription medications. 

The goals for our project were twofold:

1) Predict whether a prescription medication request would be accepted or rejected by insurance.
2) If accepted, predict the amount of money the patient will likely be required to pay for the prescription.

Stakeholders for this project include CoverMyMeds, as well as patients and clinicians. By being able to know whether a medication is likely to be accepted and how much the patient will have to pay, medical professionals can make informed decisions at the point of prescription, especially when multiple medications may be available. 

* add presentation link here * 

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

add methods and results for models here, link to jupyter notebook for goal 1

### Goal 2: Predicting required patient pay

add methods and results for models here, link to jupyter notebook for goal 2

### Conclusions and Future Directions

#### Future steps
Build a tool that allows providers to see 
* likelihood of acceptance/rejection
* cost of the medication to the patient
* potential alternative prescriptions for the diagnosis with better odds of being accepted and/or a lower cost to the patient
