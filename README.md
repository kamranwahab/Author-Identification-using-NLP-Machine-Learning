# 📚 Author Identification using NLP & Machine Learning

<p align="center">
  <img src="https://img.shields.io/badge/NLP-Text%20Classification-blue" />
  <img src="https://img.shields.io/badge/Feature-TF--IDF%20%7C%20Char%20n--grams-orange" />
  <img src="https://img.shields.io/badge/Model-Naive%20Bayes%20%7C%20SVM-green" />
  <img src="https://img.shields.io/badge/Dataset-Project%20Gutenberg-purple" />
  <img src="https://img.shields.io/badge/Status-Completed-success" />
</p>

---

## 🔍 Introduction

Author Identification is a classical **Natural Language Processing (NLP)** problem where the goal is to predict the **author of a text** based on writing style rather than topic.

In this project, we build a **complete end-to-end author identification system** using:
- Real public-domain literary texts
- Careful text preprocessing
- Multiple feature extraction techniques
- Traditional machine learning models

Despite not using deep learning, the system achieves **up to 95–99% accuracy**, showing the strength of classical NLP techniques when applied correctly.

---

## 🎯 Objectives

- Build a **real-world NLP classification pipeline**
- Learn how to **collect and clean textual data**
- Explore **word-level and character-level features**
- Compare multiple **machine learning models**
- Understand which features best capture **author writing style**
- Evaluate models using standard metrics

---

## 📂 Dataset


### 📌 Data Source
- **Project Gutenberg** (Public Domain Literary Texts)

---

### 📌 Authors Included
- William Shakespeare  
- Jane Austen  
- Charles Dickens  
- Mark Twain  
- Arthur Conan Doyle  
- H. G. Wells  
- Oscar Wilde  

---

### 📌 Dataset Preparation
- Multiple books downloaded per author
- Gutenberg headers, footers, and licenses removed
- Text split into **200–400 word snippets**
- Balanced dataset (~150 snippets per author)

---

### 📌 Dataset Size
- **Total samples:** ~1050  
- **Number of classes:** 7 authors  
- **Class distribution:** Balanced  

---

## 🧹 Preprocessing Steps

- Removal of **Gutenberg boilerplate text**
- Conversion to **lowercase**
- **Token cleaning** (numbers & special characters removed)
- **Optional lemmatization** to normalize words
- Paragraph chunking into uniform-length snippets

These steps ensure the model learns **author style**, not formatting or noise.

---

## 🧠 Feature Engineering

We experimented with multiple text representations:

- **TF-IDF Vectorization**
  - Word n-grams (unigram, bigram)
  - Character n-grams (3–5 length)

- **CountVectorizer**
  - Raw word frequency counts (baseline)

📌 **Key Insight:**  
Character n-grams capture punctuation, spelling habits, and stylistic patterns — making them especially powerful for authorship attribution.

---

## 🤖 Models Used

- Multinomial **Naïve Bayes**
- **Logistic Regression**
- **Linear Support Vector Machine (LinearSVC)**
- **SGDClassifier**

---

### 🔧 Model Training & Optimization
- Train/Test Split: **80 / 20 (stratified)**
- Cross-validation
- **GridSearchCV** & **HalvingGridSearchCV**
- Hyperparameter tuning for each model

---

## 📊 Results Summary

---

| **Model / Vectorizer**                | **Feature Type** | **Accuracy** | **Precision (avg)** | **Recall (avg)** | **F1-score (avg)** | **Notes**                               |
| ------------------------------------- | ---------------- | ------------ | ------------------- | ---------------- | ------------------ | --------------------------------------- |
| **Naïve Bayes (TF-IDF)**              | Word n-grams     | 0.989        | 0.99                | 0.99             | 0.99               | Excellent baseline with word TF-IDF     |
| **Naïve Bayes (CountVectorizer)**     | Word counts      | 0.94         | 0.94                | 0.93             | 0.93               | Slightly lower without TF-IDF weighting |
| **LinearSVC (Char n-grams)**          | Char 3–5 grams   | **0.957**    | 0.96                | 0.96             | 0.96               | Best overall (stylistic features)       |
| **Logistic Regression (Word TF-IDF)** | Word n-grams     | 0.93         | 0.93                | 0.93             | 0.93               | Strong linear baseline                  |
| **SGDClassifier (Word TF-IDF)**       | Word n-grams     | 0.91         | 0.91                | 0.90             | 0.90               | Good performance, slightly less stable  |

---

## 🏆 Key Takeaways

- Character-level features outperform word-only features for author identification
- Linear SVM provides the best balance between accuracy and stability
- Clean preprocessing and balanced data are critical
- Traditional ML models can rival deep learning for stylistic NLP tasks

---



## 🛠 Tools & Technologies

- Python  
- scikit-learn  
- pandas  
- numpy  
- matplotlib  
- NLTK  
- Requests  
- Google Colab  

---


## 📌 Conclusion

This project demonstrates a **complete and professional NLP pipeline** for author identification.  
By combining real data, thoughtful preprocessing, and optimized classical machine learning models, the system achieves **high accuracy and interpretability**, making it suitable for academic submission and portfolio presentation.
