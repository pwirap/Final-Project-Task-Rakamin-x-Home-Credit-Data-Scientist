![image](https://github.com/pwirap/Final-Project-Task-Rakamin-x-Home-Credit-Data-Scientist/assets/99533745/1411e9c5-baeb-4a8a-b1f1-74a41977f732)# Final-Project-Task-Rakamin-x-Home-Credit-Data-Scientist
Predicting customer late in making payment sUsing Machine Learning

# Background and Objective
The target variable delves into identifying clients experiencing payment challenges, particularly those with delayed payments surpassing a set threshold (X days) on at least one initial installment (Y) of a loan. Crucial for financial institutions, this variable aids in assessing individual creditworthiness and risk. The primary objective involves crafting a predictive model or strategy to accurately pinpoint clients prone to payment difficulties. Understanding the root causes behind initial late payments enables the company to diminish default risks, enhance customer retention, curtail associated costs, and refine decision-making processes. Analyzing historical data encompassing payment behaviors, loan attributes, economic indicators, and potential external factors will pave the way for tailored interventions, personalized customer support, and targeted programs aimed at preemptively addressing payment challenges, thereby benefiting both the company and its clientele.

# Scope of problem
![image](https://github.com/pwirap/Final-Project-Task-Rakamin-x-Home-Credit-Data-Scientist/assets/99533745/c52b24d4-f164-4d22-aa9d-9edd408e7886)

To mitigate a potential loss of $13,399,180,000 (8%) due to customer late payments, implementing a machine learning-based strategy to identify and address customers with high potential for late payments could significantly reduce these losses.

# Data Selection
1. SK_ID_CURR
2. NAME_CONTRACT_TYPE
3. AMT_CREDIT
4. TARGET
5. CNT_FAM_MEMBERS
6. CODE_GENDER
7. DAYS_BIRTH
8. FLAG_OWN_REALTY,  FLAG_OWN_CAR, NAME_HOUSING_TYPE, NAME_INCOME_TYPE, AMT_INCOME_TOTAL, AMT_ANNUITY
9. DEF_30_CNT_SOCIAL_CIRCLE,  DEF_60_CNT_SOCIAL_CIRCLE 
10. OCCUPATION_TYPE
11. NAME_FAMILY_STATUS

# Exploratory Data Analysis
## Compare User Late Payments in Income Type

![image](https://github.com/pwirap/Final-Project-Task-Rakamin-x-Home-Credit-Data-Scientist/assets/99533745/bd25b4d1-838d-4751-8f18-a1b2ae862f24)

INSIGHT
1. Maternity leave has the highest value of late payments, it has 50% customer that late payments
2. If look at maternity leave, it has the lowest income compared to the others. Childbirth and pregnancy-related medical care can incur significant costs.

## Compare User Late Payments in Social Circles

![image](https://github.com/pwirap/Final-Project-Task-Rakamin-x-Home-Credit-Data-Scientist/assets/99533745/4b8be541-a76f-4f72-b9fb-8f32bd2af157)

INSIGHT
1. Social circles influence the culture in the environment whether payments are late or not
2. It can be seen that, the more social circles are late in paying, the more customers are also late in making payments.
3. Where it can be seen that there are 11 customers who are late paying, these customers also failed to pay


# Data Preparation
## Checking for Null Values, Data Types, Value in every Columns and Unique Value in ID
1. There are some null values in the OCCUPATION_TYPE,DEF_30_CNT_SOCIAL_CIRCLE,DEF_60_CNT_SOCIAL_CIRCLE
2. The SK_ID_CURR feature should be converted to a object data type
3. There is no duplicated data in SK_ID_CURR indicated that the customer is unique

## Checking for Data Duplicates
1. There are no duplicate data

# Data Preprocessing
## Handling Type Data
Perform in SK_ID_CURR 

## Handling Missing Value
Data with missing values ​​will be taken out because there is still enough data

## Feature Engineering
1. YEARS : calculate how old the customer is (DAYS_BIRTH/365)
2. TOTAL_LATE_PAYMENT_SOCIAL_CIRCLE : calculate the total number of customers in the neighborhood who are late in making payments (DEF_30_CNT_SOCIAL_CIRCLE + DEF_60_CNT_SOCIAL_CIRCLE)
**features that have been carried out feature engineering will be taken out**

## Label Encoding
Label encoding will be carried out on the following features :
1. NAME_CONTRACT_TYPE
2. CODE_GENDER
3. FLAG_OWN_CAR
4. FLAG_OWN_REALTY
5. NAME_HOUSING_TYPE
6. NAME_FAMILY_STATUS
7. NAME_INCOME_TYPE
8. OCCUPATION_TYPE
9. NAME_EDUCATION_TYPE

## Class Imbalanced
because the differences in labels 1 and 0 are very different, class imbalanced will be carried out using SMOTE

![image](https://github.com/pwirap/Final-Project-Task-Rakamin-x-Home-Credit-Data-Scientist/assets/99533745/51e7b60a-323c-4bb0-8457-1d208db2421f)

## Split Data
The data will be split, where 70% is data train and 30% is data test

## Standardization
because some features, such as 'AMT_CREDIT','AMT_ANNUITY','AMT_INCOME_TOTAL','YEARS' are not normally distributed and have a long range, standardization will be carried out to increase accuracy during experiments using several machine learning models

## Outlier Handling
Because there are some feature is having a big large data, Outlier handling in data Train must be doing

# Selected Model

![image](https://github.com/pwirap/Final-Project-Task-Rakamin-x-Home-Credit-Data-Scientist/assets/99533745/f327b9f2-bb4b-4508-8b99-0786765bffa5)

1. Among the various machine learning models that have been explored, XGBoost has been selected as the top-performing model. Following this, hyperparameter tuning will be conducted after standardization to mitigate the risk of overfitting.
2. because the existing data has empty values, and the data does not have a normal distribution, and has good performance in accuracy and recall which does not indicate over fitting, XGBoost is the machine learning model used

# Confusion Matrix

![image](https://github.com/pwirap/Final-Project-Task-Rakamin-x-Home-Credit-Data-Scientist/assets/99533745/e6239c66-766d-4c84-a09f-4fd24e28cc4c)

# Business Recommendation

1. **Collaboration with Healthcare Providers or Insurers**, Consider collaborating with a health care provider or insurance company to provide specific information or solutions regarding the costs of medical care related to pregnancy and birth. This could be providing information about health insurance programs, affordable health services, or payment options related to medical care.
2. **Improved Risk Evaluation**, Update the risk evaluation process to identify potential customers who are at risk of failure to pay, especially in areas that have the potential to make late payments

# Business Simulation

![image](https://github.com/pwirap/Final-Project-Task-Rakamin-x-Home-Credit-Data-Scientist/assets/99533745/b7be0e62-bd3a-4359-8ec6-8ae4cbd2bea1)

By applying the machine learning model that has been created, it will be predicted that customers who are late in making payments, which are marked with (1), will carry out certain treatments, so that customers are not late in making their payments. With this machine learning model, company will get a profit of 2,155,181,000.
