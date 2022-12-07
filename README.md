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

The CoverMyMeds dataset includes close to 14 million observations of (simulated) claim billing data for prescription medications, including whether the claim was accepted or rejected, and how much the patient paid as a co-pay for the prescription. 

The dataset is quite imbalanced when it comes to acceptance and rejection rates. Luckily for patients, most claims for prescriptions are accepted:



add descriptive stats and plots here, link to exploratory data analysis jupyter notebook

### Goal 1: Predicting likelihood of acceptance/rejection

add methods and results for models here, link to jupyter notebook for goal 1

### Goal 2: Predicting required patient pay

add methods and results for models here, link to jupyter notebook for goal 2

### Conclusions and Future Directions
 TBD
