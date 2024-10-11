# Sure Tomorrow Insurance - Machine Learning for Insurance Claims

### [Link to Project](https://github.com/arr225/Data_Projects_TripleTen/blob/dbc11f2b36bf8e0ffafe7885a4a3145f3e3b08d2/Sure%20Tomorrow%20Insurance%20-%20Machine%20Learning%20for%20Insurance%20Claims/Sure%20Tomorrow%20Insurance%20-%20Machine%20Learning%20for%20Insurance%20Claims%20Project.ipynb)

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset and Features](#dataset-and-features)
- [Methodology](#methodology)
- [Visuals](#visuals)
- [Results](#results)
- [Suggestions for Improvement](#suggestions-for-improvement)

## Project Overview
**Sure Tomorrow Insurance** sought to improve their operations through several tasks aided by Machine Learning. This project aims to:
1. **Find similar customers** to aid in targeted marketing efforts.
2. **Predict customer likelihood** of receiving insurance benefits, comparing model performance to that of a dummy classifier.
3. **Predict the number of benefits** using linear regression.
4. **Protect clients' personal data** through data masking techniques while preserving model accuracy.

The focus of this project was not just on developing predictive models but also ensuring that privacy-preserving techniques did not impact performance.

## Dataset and Features
The dataset used in this project is stored in `/datasets/insurance_us.csv`. It contains personal information about clients, such as:
- **Features:**
  - Gender (binary)
  - Age
  - Salary
  - Number of family members
- **Target:** 
  - Number of insurance benefits received by an insured person over the past five years.

The dataset was cleaned and preprocessed to ensure it was free from missing values and outliers before model training.

## Methodology
### Task 1: Finding Similar Customers
- A **K-Nearest Neighbors** algorithm was implemented, testing various distance metrics (Manhattan and Euclidean) and data scaling techniques.
- **Conclusion:** Scaling the data provided more reliable results, highlighting the importance of data preprocessing.

### Task 2: Predicting Benefit Likelihood
- A binary classification model was trained to predict whether a customer would receive an insurance benefit.
- Models tested included **KNN classifiers** with scaled and unscaled data, compared to a **dummy classifier**.

### Task 3: Predicting the Number of Benefits
- A **Linear Regression model** was developed to predict how many insurance benefits a customer was likely to receive.
- **Conclusion:** Both scaled and unscaled data were used, with scaling improving model performance.

### Task 4: Data Masking for Privacy
- Personal data was obfuscated using a matrix multiplication technique. Despite data masking, the model's performance remained intact, proving that personal information can be protected without affecting predictive power.

## Visuals

### Task 1: Similar Customers Results
![Task 1: Similar Customers Results](https://github.com/arr225/Data_Projects_TripleTen/blob/d6bf6e5e3751ec3f22527c05cf2037e8aec9dabf/Sure%20Tomorrow%20Insurance%20-%20Machine%20Learning%20for%20Insurance%20Claims/Similar%20Customers%20Results.png)

*Description:* This visual shows the output of the customer similarity search using Euclidean and Manhattan distance metrics. It displays the top results for customers most similar to the given customer based on gender, age, income, and family members.

---

### Task 2: KNN Classifier Results
![Task 2: KNN Classifier Results](https://github.com/arr225/Data_Projects_TripleTen/blob/74e34965395eed96f2882bc9ac70a06b6f095c23/Sure%20Tomorrow%20Insurance%20-%20Machine%20Learning%20for%20Insurance%20Claims/KNN%20Classifier%20Results.png)

*Description:* This screenshot displays the results from the KNN Classifier model used to predict whether a customer is likely to receive an insurance benefit. The F1 Score was calculated for different values of k (from 1 to 10) for both original and scaled data. The results indicate that the scaled data performs better across most values of k, with the highest F1 Score reaching 0.9457 at k=6. Additionally, the performance of a Dummy Classifier was evaluated for comparison. The Dummy Classifier's F1 Scores were significantly lower across all probabilities tested, showing that the KNN model performs substantially better. 

---

### Task 3: Linear Regression Performance
![Task 3: Linear Regression Performance](https://github.com/arr225/Data_Projects_TripleTen/blob/ab3ece06071a5d333423bb5e3020ea5c7090efb4/Sure%20Tomorrow%20Insurance%20-%20Machine%20Learning%20for%20Insurance%20Claims/Linear%20Regression%20Performance.png)

*Description:* The screenshot above shows the results of applying linear regression to predict the number of insurance benefits a new customer is likely to receive. The performance is evaluated on both unscaled and scaled data.

- **Original and Scaled Training Data**: The first 5 rows of the original and scaled training data are displayed to illustrate how scaling affects the feature values.
- **Weights for Unscaled and Scaled Data**: The regression weights for both unscaled and scaled data are provided, showing the relationship between features and target variables in both cases.
- **Model Evaluation**: The model's performance is assessed using the following metrics:
  - **RMSE (Root Mean Squared Error)**: A lower value of RMSE indicates better performance. The model produced an RMSE of 0.24 for both scaled and unscaled data.
  - **R² (Coefficient of Determination)**: Indicates how well the model explains the variance in the target variable, with an R² of 0.43-0.44 for both scaled and unscaled data.

This analysis demonstrates that scaling does not significantly affect the model's performance, as the RMSE and R² values remain consistent across both scaled and unscaled data.

## Results
- **KNN for Customer Similarity:** Successfully identified similar customers, with scaling improving results.
- **Benefit Likelihood Prediction:** The KNN model, particularly with scaled data, significantly outperformed the dummy classifier, achieving an F1 score of 0.9457.
- **Linear Regression:** The model accurately predicted the number of benefits, with an RMSE of 0.23.
- **Data Obfuscation:** Successfully masked personal data without compromising model performance, protecting client information while maintaining accuracy.

## Suggestions for Improvement
- **Further Exploration of Models:** Additional models such as **Random Forests** or **Gradient Boosting** could be implemented to explore whether they outperform the current KNN and Linear Regression models.
- **Advanced Data Masking:** Investigating more advanced techniques, such as **differential privacy**, could further enhance the protection of client data.
- **Ensemble Models:** Combining multiple models could provide better predictive power, especially for predicting benefit likelihood.
