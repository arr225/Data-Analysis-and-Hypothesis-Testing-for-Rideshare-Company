# Sentiment Analysis for Movie Reviews

### [Link to Project](https://github.com/arr225/Data_Projects_TripleTen/blob/6d9b87bbbdd60b489966af996f7174035a6cef58/Sentiment%20Analysis%20for%20Movie%20Reviews/Film%20Junky%20Union%20%E2%80%93%20Sentiment%20Analysis%20for%20Movie%20Reviews%20Project.ipynb)

## Table of Contents
1. [Project Overview](#project-overview)
2. [Dataset and Features](#dataset-and-features)
3. [Methodology](#methodology)
4. [Visuals](#visuals)
5. [Results](#results)
6. [Suggestions for Improvement](#suggestions-for-improvement)

---

## 1. Project Overview
The **Film Junky Union**, a community for classic movie enthusiasts, aimed to build a sentiment analysis system to filter and categorize movie reviews. The goal was to develop a machine learning model that could accurately classify reviews as positive or negative, reaching an F1 score of at least **0.85**. This project explored various machine learning models to help automate review classification for the platform.

---

## 2. Dataset and Features
The dataset used for this project contains movie reviews from IMDb, with corresponding polarity labels (0 for negative, 1 for positive).

- **Source**: Andrew L. Maas et al., "Learning Word Vectors for Sentiment Analysis", ACL 2011.
- **Data File**: `imdb_reviews.tsv`

### Key Features:
- **review**: The text of the movie review.
- **pos**: Target variable where '0' indicates a negative review and '1' indicates a positive review.
- **ds_part**: Identifies whether the review is part of the training or test dataset.

The dataset was cleaned and preprocessed for model training.

---

## 3. Methodology
### Data Preprocessing:
- Reviews were cleaned by converting them to lowercase, removing punctuation, and eliminating stopwords.
- The text data was transformed into vectors using **TF-IDF** (Term Frequency-Inverse Document Frequency).

### Exploratory Data Analysis (EDA):
- A balanced dataset was confirmed, with approximately equal numbers of positive and negative reviews.

### Models Used:
1. **Model 0 - Constant (DummyClassifier)**:
   - Baseline model used with the 'most_frequent' strategy.
   - Provided a baseline F1 score and accuracy to compare other models against.

2. **Model 1 - NLTK, TF-IDF and Logistic Regression**:
   - Used TF-IDF vectorization for text feature extraction.
   - Logistic Regression model was trained and tested, achieving improved results over the baseline.

3. **Model 3 - spaCy, TF-IDF and Logistic Regression**:
   - Used spaCy for lemmatization and tokenization in text preprocessing.
   - Logistic Regression was retrained using the spaCy-preprocessed data and TF-IDF features.

4. **Model 4 - spaCy, TF-IDF and LightGBMClassifier**:
   - SpaCy was again used for preprocessing, and TF-IDF features were extracted.
   - LightGBMClassifier was employed for training, providing significant improvements in performance.

---

## 4. Visuals

### Review Distribution
![Distribution of Reviews](https://github.com/arr225/Data_Projects_TripleTen/blob/98c3988c7dfe124441f075284916e7f5f79dcd9e/Sentiment%20Analysis%20for%20Movie%20Reviews/Distribution%20of%20number%20of%20reviews%20per%20movie%20with%20the%20exact%20counting%20and%20KDE.png)  

*Description:* This section of the analysis explores the distribution of the number of reviews per movie using both a bar plot and a KDE plot. The bar plot (on the left) provides an exact count of how many movies received a specific number of reviews, while the KDE plot (on the right) estimates the distribution of reviews across movies using a continuous probability function. From the KDE plot, we can observe that the majority of movies have between 5 to 15 reviews, with a peak around 7 reviews per movie. This provides valuable insights into how review counts are distributed, and can inform future analysis or model improvements that rely on understanding the balance or imbalance in review data.

---

### Model Performance
![Model 0 - Constant (DummyClassifier)](https://github.com/arr225/Data_Projects_TripleTen/blob/0113a0f8fad294d0e9d4e4dbcb0e4d0bb653e037/Sentiment%20Analysis%20for%20Movie%20Reviews/Model%200%20-%20Constant%20(DummyClassifier).png)  
![Model 1 - NLTK, TF-IDF and Logistic Regression](https://github.com/arr225/Data_Projects_TripleTen/blob/0b7b744ca3119af9cfa79d8b810391dc7d2a6eb5/Sentiment%20Analysis%20for%20Movie%20Reviews/Model%201%20-%20NLTK%2C%20TF-IDF%20and%20Logistic%20Regression.png) 
![Model 3 - spaCy, TF-IDF and Logistic Regression](https://github.com/arr225/Data_Projects_TripleTen/blob/842e96d02a058c70de3d1d244e2eb2db86b4000d/Sentiment%20Analysis%20for%20Movie%20Reviews/Model%203%20-%20spaCy%2C%20TF-IDF%20and%20Logistic%20Regression.png) 
![Model 4 - spaCy, TF-IDF and LightGBMClassifier)](https://github.com/arr225/Data_Projects_TripleTen/blob/e09785ed156f00bc3f6480723cb2d73425d81438/Sentiment%20Analysis%20for%20Movie%20Reviews/Model%204%20-%20spaCy%2C%20TF-IDF%20and%20LightGBMClassifier.png) 

*Description:* The F1 score of each model is displayed, comparing the performance of Logistic Regression with TF-IDF and LightGBM. The best-performing model achieved an F1 score of **0.88**.

---

## 5. Results
- **Logistic Regression** using spaCy preprocessing produced the best results, achieving an F1 score of **0.88**.
- The model successfully classified positive and negative reviews with high accuracy, making it suitable for automating the review filtering process.

---

## 6. Suggestions for Improvement

1. **Use of Advanced Embeddings**: Consider implementing word embeddings like **Word2Vec** or **BERT** to capture deeper semantic meaning within the reviews.
2. **Hyperparameter Tuning**: Further fine-tuning of model hyperparameters could enhance the performance of the classification models.
3. **Deployment**: The next step would be deploying this model using an API to classify reviews in real-time.
