# Customer Churn Prediction for Interconnect Telecom

[Link to the project](https://github.com/arr225/Data_Projects_TripleTen/blob/12c27989f10925328238261f263455dd3f75562f/Customer%20Churn%20Prediction/Interconnect%20Telecom%20%E2%80%93%20Customer%20Churn%20Prediction%20Project.ipynb)

## Table of Contents
1. [Project Overview](#project-overview)
2. [Dataset and Features](#dataset-and-features)
3. [Methodology](#methodology)
4. [Visuals](#visuals)
5. [Results](#results)
6. [Suggestions for Improvement](#suggestions-for-improvement)

## Project Overview

Interconnect Telecom, a major service provider offering landline communication and internet services, aims to predict customer churn to take proactive measures such as offering promotions and special plans to retain customers. The project uses various datasets related to customer contracts, personal data, internet, and phone services to build machine learning models that can forecast which customers are likely to churn. The target variable is churn (whether a customer has left the company or is still active). 

The goal is to develop a model that reaches an AUC-ROC score of at least 0.88, helping the company effectively reduce customer churn and improve retention.

## Dataset and Features

The datasets provided consist of the following:

1. **contract.csv** — This contains contract information such as:
   - `customerID`: Unique ID for each customer
   - `BeginDate`: Contract start date
   - `EndDate`: Contract end date (used to identify churn)
   - `Type`: Type of contract (monthly, one-year, two-year)
   - `PaperlessBilling`: Whether the customer uses paperless billing
   - `PaymentMethod`: How the customer makes payments
   - `MonthlyCharges`: Monthly charge for the customer
   - `TotalCharges`: Total charges during the customer's tenure

2. **personal.csv** — Personal details of customers, including:
   - `customerID`: Unique ID for each customer
   - `gender`: Gender of the customer
   - `SeniorCitizen`: Whether the customer is a senior citizen
   - `Partner`: Whether the customer has a partner
   - `Dependents`: Whether the customer has dependents

3. **internet.csv** — Information related to internet services, such as:
   - `customerID`: Unique ID for each customer
   - `InternetService`: Type of internet service (DSL, Fiber, etc.)
   - Various features for online security, backups, tech support, etc.

4. **phone.csv** — Data on phone services:
   - `customerID`: Unique ID for each customer
   - `MultipleLines`: Whether the customer has multiple lines

The target feature is determined based on the `EndDate`. If `EndDate` is "No," the customer is still active. Otherwise, they are considered churned.

## Methodology

1. **Data Preparation**: 
   - Merged the four datasets based on the `customerID` column.
   - Handled missing values by filling service-related columns with "No" to indicate a lack of subscription to those services.
   - Converted columns like `BeginDate` and `EndDate` to datetime formats and created a target variable `Churn` based on whether the customer has churned.

2. **Exploratory Data Analysis (EDA)**:
   - Analyzed the distribution of customer tenure, monthly and total charges, and churn rates.
   - Explored how various factors such as contract type, payment method, and services used affect customer churn.

3. **Model Training**:
   - Built multiple models, including Logistic Regression and Random Forest, and evaluated their performance using AUC-ROC and accuracy metrics.
   - Tuned hyperparameters to optimize model performance and conducted cross-validation to ensure generalization.

4. **Model Evaluation**:
   - AUC-ROC was used as the primary evaluation metric to gauge how well the models distinguish between churned and non-churned customers.
   - Accuracy, precision, recall, and F1 scores were also calculated to provide a comprehensive view of model performance.

## Visuals

Here are a few key visuals from the project:

**Distribution of TotalCharges and MonthlyCharges**:
   ![TotalCharges and MonthlyCharges Distribution](https://github.com/arr225/Data_Projects_TripleTen/blob/91c5e41fa3086062a54ed05b2c9a998998933eb9/Customer%20Churn%20Prediction/Distribution%20of%20TotalCharges%20and%20MonthlyCharge.png)

   *Description*:

**Churn Rate Analysis**:
   ![Churn Rate](#)

   *Description*:

**Contract Type vs. Churn**:
   ![Contract Type and Churn](#)

   *Description*:

**Payment Method vs. Churn**:
   ![Payment Method and Churn](#)

   *Description*:

## Results

- The Random Forest model with tuned hyperparameters achieved the best performance, with an **AUC-ROC score of 0.8827** and an accuracy of 82.29% on the validation set.
- Customers with higher monthly charges and those on month-to-month contracts were more likely to churn.
- Payment method also played a role, with customers using electronic checks having a higher likelihood of churning compared to those on automatic payments.

## Suggestions for Improvement

1. **Focus on High-Churn Segments**: The company should prioritize retention strategies for customers with month-to-month contracts and higher monthly charges, as these groups are most likely to churn.
2. **Incentivize Long-Term Contracts**: Offering promotions for long-term contracts may reduce churn, especially for new customers.
3. **Target Electronic Check Users**: Customers who use electronic checks for payments are more likely to churn. Introducing incentives for switching to automated payments could improve retention.
4. **Enhanced Data Collection**: Collecting additional data on customer satisfaction or reasons for churn could help improve model performance by introducing more predictive features.
