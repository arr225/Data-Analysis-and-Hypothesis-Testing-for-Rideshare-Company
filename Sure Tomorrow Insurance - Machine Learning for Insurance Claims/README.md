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
![Task 1: Similar Customers Results](#)
![Task 2: KNN Classifier Results](#)
![Task 3: Linear Regression Performance](#)

## Results
- **KNN for Customer Similarity:** Successfully identified similar customers, with scaling improving results.
- **Benefit Likelihood Prediction:** The KNN model, particularly with scaled data, significantly outperformed the dummy classifier, achieving an F1 score of 0.9457.
- **Linear Regression:** The model accurately predicted the number of benefits, with an RMSE of 0.23.
- **Data Obfuscation:** Successfully masked personal data without compromising model performance, protecting client information while maintaining accuracy.

## Suggestions for Improvement
- **Further Exploration of Models:** Additional models such as **Random Forests** or **Gradient Boosting** could be implemented to explore whether they outperform the current KNN and Linear Regression models.
- **Advanced Data Masking:** Investigating more advanced techniques, such as **differential privacy**, could further enhance the protection of client data.
- **Ensemble Models:** Combining multiple models could provide better predictive power, especially for predicting benefit likelihood.
