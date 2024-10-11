# Sentiment Analysis for Movie Reviews

### [Link to Project](#)

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
- **Logistic Regression** with TF-IDF vectorization.
- **LightGBM Classifier** with spaCy preprocessing.
- Custom reviews were also classified using the trained models for performance validation.

---

## 4. Visuals

### Review Distribution
![Distribution of Reviews](#)  
*Description:* This plot shows the distribution of positive and negative reviews, confirming that the dataset is balanced.

---

### Model Performance
![Model Performance](#)  
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
