# HEALTH INSURANCE CROSS SELL PREDICTION
Predicting whether a customer would be interested in buying Vehicle Insurance so that the company can then accordingly plan its communication strategy to reach out to those customers and optimise its business model and revenue.


---

## Table of Content
  * [Summary](#summary)
  * [Abstract](#abstract)
  * [Problem Statement](#problem-statement)
  * [Data Description](#data-description)
  * [Project Outline](#project-outline)
    * [Knowing the Data](#knowing-the-data)
    * [Understanding the Variables](#understanding-the-variables)
    * [Data Wrangling](#data-wrangling)
    * [Data Visualization](#data-visualization)
    * [Feature Engineering and Data Pre processing](#feature-engineering-and-data-pre-processing)
    * [Machine Learning Models](#Machine-Learning-Models)
  * [Conclusion](#conclusion)
  

---

## Summary
The dataset used for this analysis contains 381109 rows and 12 columns, consisting of 6 integer, 3 object, and 3 float columns. The data has no null or duplicate values. The mean age of the individuals in the dataset is approximately 38 years, the average annual premium is around 30564, and the average vintage (i.e., number of days that the customer has been associated with the company) is around 154 days. There is a significant amount of variation in the data, as indicated by the standard deviation. The age of the individuals ranges from 20 to 85 years, the annual premium ranges from 2630 to 540165, and the vintage ranges from 10 to 299 days.

The maximum age of the individuals surveyed was 85 years old, and all of these respondents indicated that they were not interested in purchasing health insurance. As the age of the respondents increased, their level of interest in purchasing health insurance decreased. Both male and female respondents had the same minimum and maximum age ranges. However, there were more females with driving licenses compared to males. There are more male customers than female customers who have health insurance, indicating that males are more likely to purchase health insurance. Customers with a driving license are more inclined to consider purchasing health insurance, while those who were previously insured may not necessarily do so. Customers with vehicles aged between 1-2 years are more likely to buy health insurance, while those who have experienced vehicle damage are also more inclined to purchase insurance due to the associated maintenance costs.

Channel 152.0 appears to outperform other channels in terms of policy sales, although the meaning of policy channel codes is unknown. Customers aged between 38 to 50 are more likely to respond to insurance sales, while those aged between 20 to 30 are less likely to do so. 45.8% of customers have been previously insured, and only 12.3% of customers have shown interest in purchasing health insurance. Age and policy sales channels appear to be highly correlated, and there are outliers in the annual premium data.

After addressing the presence of outliers using the interquartile range method and multicollinearity using the variance inflation factor method, the data was split into training and testing sets. The Synthetic Minority Over-sampling Technique (SMOTE) was used to balance the dataset. A decision tree model performed the best out of all the models evaluated, with a training accuracy of 0.986 and a validation accuracy of 0.876, indicating that it is able to generalize well to unseen data. Logistic regression also performed well, with a validation accuracy of around 0.80, but not as well as the decision tree model. Hyperparameter tuning using random search and grid search did not lead to significant improvements in performance for any of the models.

In conclusion, based on the evaluation of the models, the decision tree model may be recommended for this project as it provides a high level of accuracy and is able to generalize well. However, further analysis and evaluation may be necessary to determine the best model for this specific project.

## Abstract
An insurance policy is an arrangement by which a company undertakes to provide a guarantee of compensation for specified loss, damage, illness, or death in return for the payment of a specified premium. There are multiple factors that play a major role in capturing customers for any insurance policy. Here we have information about demographics such as age, gender, region code, and vehicle damage, vehicle age, annual premium, policy sourcing channel.
Based on the previous trend, this data analysis and prediction with machine learning models can help us understand what are the reasons for news popularity on social media and obtain the best classification model.

## Problem Statement
Our client is an Insurance company that has provided Health Insurance to its customers. Now they need the help in building a model to predict whether the policyholders (customers) from the past year will also be interested in Vehicle Insurance provided by the company.

An insurance policy is an arrangement by which a company undertakes to provide a guarantee of compensation for specified loss, damage, illness, or death in return for the payment of a specified premium. A premium is a sum of money that the customer needs to pay regularly to an insurance company for this guarantee.

*Building a model to predict whether a customer would be interested in Vehicle Insurance is extremely helpful for the company because it can then accordingly plan its communication strategy to reach out to those customers and optimize its business model and revenue.*


## Data Description
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
## Project Outline

### Knowing the Data
There are 381109 rows and 12 columns. We also checked and found there are no null and dublicate values. The dataframe consist of 6 integer, 3 object and 3 float columns.

### Understanding the variable
Based output, we can conclude that the mean age of the individuals in the dataset is around 38 years, the average annual premium is around 30564, and the average vintage (i.e., number of days that the customer has been associated with the company) is around 154 days. The standard deviation shows that there is a considerable amount of variation in the data. Additionally, the minimum and maximum values show that the age of the individuals ranges from 20 to 85 years, the annual premium ranges from 2630 to 540165, and the vintage ranges from 10 to 299 days.

### Data Wrangling
Based on our observations, we found that the maximum age of the individuals we surveyed was 85 years old, and we noted that all of these respondents indicated that they were not interested in purchasing health insurance. Additionally, we noticed that as the age of the respondents increased, their level of interest in purchasing health insurance decreased. Both male and female respondents had the same minimum and maximum age ranges. However, we also observed that there were more percentage of females with driving licenses compared to males.

### Data Visualization
Based on the available data, we can observe that there are more male customers than female customers who have health insurance. It appears that males are more likely to purchase health insurance. Customers with a driving license are more inclined to consider purchasing health insurance, while those who were previously insured may not necessarily do so. Customers with vehicles aged between 1-2 years are more likely to buy health insurance, while those who have experienced vehicle damage are also more inclined to purchase insurance due to the associated maintenance costs.

Although we lack information on the meaning of policy channel codes, it appears that channel 152.0 outperforms other channels in terms of policy sales. Customers aged between 38 to 50 are more likely to respond to insurance sales, while those aged between 20 to 30 are less likely to do so.

From the data available, we can also infer that 45.8% of customers have been previously insured. Furthermore, only 12.3% of customers have shown interest in purchasing health insurance. Age and policy sales channels appear to be highly correlated, and there are some outliers in the annual premium data.

### Feature Engineering and Data Pre processing
The available data shows that the annual premium is positively skewed, indicating that the data is not normally distributed. To address the presence of outliers, the interquartile range (IQR) method was used to remove them from the dataset.

After performing one-hot encoding to convert categorical variables to numerical ones, the correlation between the variables increased. To address the issue of multicollinearity, the variance inflation factor (VIF) method was used to remove highly correlated independent variables.

Given the imbalanced nature of the data, the Synthetic Minority Over-sampling Technique (SMOTE) was used to balance the dataset by generating synthetic samples for the minority class.

Finally, the data was split into training and testing sets to build and evaluate the predictive models.

### Machine Learning Models
For modeling, we tried the various classification algorithms like:

#### Logistic Regression
Logistic regression is named for the function used at the core of the method, the logistic function.

The logistic function, also called the sigmoid function, was developed by statisticians to describe properties of population growth in ecology, rising quickly and maxing out at the carrying capacity of the environment. It’s an S-shaped curve that can take any real-valued number and map it into a value between 0 and 1, but never exactly at those limits.

#### Decision Tree 
Decision Trees are non-parametric supervised learning methods, capable of finding complex non-linear relationships in the data. Decision trees are a type of algorithm that uses a tree-like system of conditional control statements to create the machine learning model. A decision tree observes features of an object and trains a model in the structure of a tree to predict data in the future to produce output.
For classification trees, it is a tree-structured classifier, where internal nodes represent the features of a dataset, branches represent the decision rules and each leaf node represents the outcome.

#### Random Forest
Random forest is an ensemble learning method for classification, regression and other tasks that operate by constructing multiple decision trees at training time and outputting the class that is the mode of the classes (classification) or mean prediction (regression) of the individual trees.

#### AdaBoost Classifier
Boosting is a class of ensemble machine learning algorithms that involve combining the predictions from many weak learners. A weak learner is a very simple model, although has some skill on the dataset. Boosting was a theoretical concept long before a practical algorithm could be developed, and the AdaBoost (adaptive boosting) algorithm was the first successful approach for the idea.
The AdaBoost algorithm involves using very short (one-level) decision trees as weak learners that are added sequentially to the ensemble. Each subsequent model attempts to correct the predictions made by the model before it in the sequence. This is achieved by weighing the training dataset to put more focus on training examples on which prior models made prediction errors.

## Conclusion
In this data science project aimed at predicting sales for Rossmann_Stores, we evaluated the performance of various machine learning models using several metrics, including R score, Adjusted R score, Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and Mean Absolute Error (MAE).

Based on our analysis, the results show that the XGBoost model (xgb_model) achieved the highest R score of 0.980071, indicating excellent predictive capability. The Adjusted R score, which considers the complexity of the model, is also very close to the R score, suggesting that the model's performance is reliable and not heavily influenced by overfitting.

The Decision Tree model (decision_tree) demonstrated strong performance as well, with an R score of 0.972925. While slightly below the XGBoost model, it remains a competitive option for predicting store sales.

The Gradient Boosting model (gradient_boosting) follows with an R score of 0.932960. While it is less accurate than the top two models, it may still provide valuable predictions for store sales.

The Ridge model (ridge), Linear Regression model (linear_regression), and Lasso model (lasso) show similar R scores of approximately 0.903, indicating moderate predictive ability for store sales.

The AdaBoost model (AdaBoost) falls further behind, with an R score of 0.852333, suggesting limited accuracy in predicting sales for multiple stores.

Lastly, the Elastic Net model (elastic_net) performed the least favorably among all models, with an R score of 0.319279. It is apparent that this model may not be well-suited for this specific prediction task and requires further investigation or potentially different modeling approaches.

Overall, the XGBoost model stands out as the best performer, demonstrating the highest predictive accuracy for sales across multiple stores. However, it is crucial to consider other factors such as model interpretability, computational complexity, and data size when selecting the final model for deployment.



