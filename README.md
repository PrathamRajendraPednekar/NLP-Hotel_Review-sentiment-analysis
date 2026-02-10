# 🏨 Hotel Review Sentiment Analysis using NLP (Python)

This project focuses on building an **NLP-based sentiment analysis system** to automatically classify hotel reviews as **happy (positive)** or **not happy (negative)**.  
It helps hotel management understand customer feedback at scale and make **data-driven decisions** to improve service quality.

---

## 📌 Problem Statement

In the competitive hospitality industry, customer reviews play a critical role in shaping service improvements and brand reputation.  
Manual analysis of thousands of hotel reviews is **time-consuming, error-prone, and inefficient**.

The challenge is to **automatically classify hotel reviews** into sentiment categories such as:
- Happy (Positive)
- Not Happy (Negative)

This enables faster identification of customer dissatisfaction and better utilization of positive feedback.

---

## 🎯 Project Objective

To develop a **machine learning–based NLP model** that accurately classifies hotel reviews into sentiment categories and provides actionable insights to hotel management for:
- Improving customer satisfaction
- Enhancing service quality
- Supporting business decisions

---

## 🗂️ Dataset Information

- **Source:** Kaggle  
  https://www.kaggle.com/anu0012/hotel-review/data
- **Total Records:** 38,932
- **Columns:**
  - `User_ID`
  - `Description` (Review Text)
  - `Browser_Used`
  - `Device_Used`
  - `Is_Response` (Target Variable)

### Target Class Distribution
- **Happy:** 68.12%
- **Not Happy:** 31.88%

---

## 🧪 Methodology

### 1️⃣ Data Preprocessing

**Text Cleaning Steps:**
- Converted text to lowercase
- Removed punctuation, numbers, and special characters
- Removed brackets and newline characters
- Standardized text using multiple cleaning passes

**Column Reduction:**
- Removed irrelevant features:
  - `User_ID`
  - `Browser_Used`
  - `Device_Used`

Only the **review text** and **sentiment label** were retained.

---

### 2️⃣ Exploratory Data Analysis (EDA)

- Checked missing values (✔ No missing data)
- Analyzed class imbalance
- Visualized sentiment distribution using bar plots

---

### 3️⃣ Feature Extraction

- **TF-IDF Vectorization**
  - Converts textual data into numerical features
  - Highlights important words while reducing the impact of frequent common terms

---

### 4️⃣ Model Building

- **Algorithm Used:** Logistic Regression
- **Pipeline:**
  - TF-IDF Vectorizer
  - Logistic Regression Classifier
- **Train-Test Split:** 90% training, 10% testing

```python
Pipeline([
  ('vectorizer', TfidfVectorizer()),
  ('classifier', LogisticRegression(solver='lbfgs'))
])
