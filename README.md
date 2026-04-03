# NLP Text Classification Project

This project demonstrates a complete workflow for Natural Language Processing (NLP) text classification using Python, `nltk`, `scikit-learn`, and `pandas`.

## Project Overview

The goal of this project is to classify text documents into predefined categories using machine learning techniques. The process involves data loading, comprehensive NLP preprocessing, text vectorization, model training, and evaluation.

## Table of Contents

1.  [Setup and Installation](#setup-and-installation)
2.  [Download NLTK Data](#download-nltk-data)
3.  [Data Loading](#data-loading)
4.  [NLP Preprocessing](#nlp-preprocessing)
5.  [Text Vectorization](#text-vectorization)
6.  [Model Building and Training](#model-building-and-training)
7.  [Model Evaluation](#model-evaluation)

## 1. Setup and Installation

This section ensures all necessary Python libraries are installed. The following libraries are used:
*   `nltk`: For natural language processing tasks.
*   `scikit-learn`: For machine learning models and utilities.
*   `pandas`: For data manipulation and analysis.

## 2. Download NLTK Data

NLTK requires various datasets for its functionalities. This step downloads essential datasets such as tokenizers (`punkt`), stopwords (`stopwords`), and WordNet (`wordnet`).

## 3. Data Loading

The project utilizes a subset of the **20 Newsgroups dataset**, a popular dataset for text classification. Specifically, it loads documents from four categories:
*   `alt.atheism`
*   `soc.religion.christian`
*   `comp.graphics`
*   `sci.med`

The data is loaded into pandas DataFrames for easy manipulation, separating training and testing sets.

## 4. NLP Preprocessing

Text data often requires cleaning and transformation before it can be used by machine learning models. This project implements a custom preprocessing function that performs:
*   **Lowercasing**: Converts all text to lowercase.
*   **Punctuation and Number Removal**: Removes special characters and digits.
*   **Tokenization**: Breaks text into individual words.
*   **Stopword Removal**: Eliminates common words (e.g., 'the', 'is', 'a') that don't contribute much to meaning.
*   **Lemmatization**: Reduces words to their base form (e.g., 'running' -> 'run') to reduce vocabulary size and normalize text.

## 5. Text Vectorization

After preprocessing, text needs to be converted into numerical features. This project uses the **TF-IDF Vectorizer** (`TfidfVectorizer`) to transform text into a matrix of TF-IDF scores, representing the importance of words within documents relative to the entire corpus. A maximum of 5000 features are used.

## 6. Model Building and Training

A **Support Vector Machine (SVM) with a linear kernel** (`LinearSVC`) is chosen for the text classification task. This model is known for its effectiveness with high-dimensional data like text features. The model is trained on the TF-IDF vectorized training data.

## 7. Model Evaluation

The trained model's performance is evaluated on the unseen test set. Key metrics calculated include:
*   **Accuracy Score**: Overall accuracy of the model.
*   **Classification Report**: Provides detailed metrics (precision, recall, f1-score, and support) for each class, offering insights into the model's performance across different categories.
