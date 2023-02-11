# HEALTH INSURANCE CROSS SELL PREDICTION
Predicting whether a customer would be interested in buying Vehicle Insurance so that the company can then accordingly plan its communication strategy to reach out to those customers and optimise its business model and revenue.


---

## Table of Content
  * [Abstract](#abstract)
  * [Problem Statement](#problem-statement)
  * [Data Description](#data-description)
  * [Project Outline](#project-outline)
    - 1 [Data Wrangling](#data-wrangling)
    - 2 [Normalization](#normalization)
    - 3 [EDA](#eda)
    - 4 [ Encoding categorical values](#encoding-categorical-values)
    - 5 [Feature Selection](#feature-selection)
    - 6 [Model Fitting](#model-fitting)
    - 7 [Hyper-parameter Tuning](#hyper-parameter-tuning)
    - 8 [Metrics Evaluation](#metrics-evaluation)
  * [Conclusion](#conclusion)
  * [Reference](#reference)

---



# Abstract
An insurance policy is an arrangement by which a company undertakes to provide a guarantee of compensation for specified loss, damage, illness, or death in return for the payment of a specified premium. There are multiple factors that play a major role in capturing customers for any insurance policy. Here we have information about demographics such as age, gender, region code, and vehicle damage, vehicle age, annual premium, policy sourcing channel.
Based on the previous trend, this data analysis and prediction with machine learning models can help us understand what are the reasons for news popularity on social media and obtain the best classification model.

# Problem Statement
Our client is an Insurance company that has provided Health Insurance to its customers. Now they need the help in building a model to predict whether the policyholders (customers) from the past year will also be interested in Vehicle Insurance provided by the company.

An insurance policy is an arrangement by which a company undertakes to provide a guarantee of compensation for specified loss, damage, illness, or death in return for the payment of a specified premium. A premium is a sum of money that the customer needs to pay regularly to an insurance company for this guarantee.

*Building a model to predict whether a customer would be interested in Vehicle Insurance is extremely helpful for the company because it can then accordingly plan its communication strategy to reach out to those customers and optimize its business model and revenue.*


# Data Description
We have a dataset which contains information about demographics (gender, age, region code type), Vehicles (Vehicle Age, Damage), Policy (Premium, sourcing channel) etc. related to a person who is interested in vehicle insurance.
We have 381109 data points available.


| Feature Name | Type | Description |
|----|----|----|
|id| (continous) |Unique identifier for the Customer.|
|Age |(continous)| Age of the Customer.|
|Gender |(dichotomous)|Gender of the Custome|
|Driving_License |(dichotomous)|0 for customer not having DL, 1 for customer having DL.|
|Region_Code |(nominal)|Unique code for the region of the customer.|
|Previously_Insured| (dichotomous)| 0 for customer not having vehicle insurance, 1 for customer having vehicle insurance.|
|Vehicle_Age| (nominal)| Age of the vehicle.|
|Vehicle_Damage | (dichotomous)| Customer got his/her vehicle damaged in the past. 0 : Customer didn't get his/her vehicle damaged in the past.|
|Annual_Premium| (continous)| The amount customer needs to pay as premium in the year.|
|Policy_Sales_Channel| (nominal)| Anonymized Code for the channel of outreaching to the customer ie. Different Agents, Over Mail, Over Phone, In Person, etc.|
|Vintage |(continous)|Number of Days, Customer has been associated with the company.|
|**Response** (Dependent Feature)|(dichotomous)| 1 for Customer is interested, 0 for Customer is not interested.|


----
# Project Outline

## 7. Hyperparameter Tuning
