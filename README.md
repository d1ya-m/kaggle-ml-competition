# One Million Clicks Later – Video Click Prediction

## Overview
This project presents a solution to the Kaggle competition **“One Million Clicks Later”**, where the task is to predict whether a user will **click on a recommended video** in a YouTube-like feed.
The focus is on building an end-to-end ML pipeline and optimizing **accuracy**, the official leaderboard metric.

## Competition Link
🔗 **Kaggle Competition:**  
https://www.kaggle.com/competitions/one-million-clicks-later
---

## Project Structure
```
.
├── contest1.ipynb
├── data/            (git-ignored)
└── README.md
```

---

## Dataset
The dataset contains **1,000,000 user–video interaction records**.

**Task:** Binary classification — will the user click the video
**Target variable:** `clicked` (0 / 1)

**Feature groups:**
* User & video identifiers (`user_id`, `video_id`)
* Engagement signals (`watch_time_sec`, `video_duration_sec`, `liked`)
* Contextual features (`category`, `device`, `source`, `recommended`)
* Temporal features (`timestamp`)
* Submission identifier (`id`)

The training set includes `clicked`; the test set does not.

---

## Problem Statement
Given user, video, and contextual features for each recommendation, train a model that predicts whether the user will click the video, maximizing **accuracy** on unseen data.

---

## Approach

### Exploratory Data Analysis

* Analyzed click-through rate and class balance
* Studied behavior across `category`, `device`, and `source`
* Checked missing values and inconsistent labels

### Preprocessing & Feature Engineering

* Standardized `liked` values (`yes/no → 1/0`, handled invalid entries)
* Engineered behavioral features such as **watch ratio**
* Encoded categorical variables (`category`, `device`, `source`)
* Extracted time-based features from `timestamp`
* Dropped sparse text features (`comment`) for baseline models

---

## Models Tried

* Baseline Logistic Regression with regularization to establish a linear performance benchmark.
* Tree-based models (Decision Tree and simple ensembles) to capture non-linear feature interactions.
* Boosted ensemble model selected as the final submission for improved predictive performance.
* Threshold-tuned variants of the best-performing model to maximize validation accuracy.

---

## Training & Evaluation
* Split training data into **train/validation** sets
* Compared models using **Accuracy** (primary metric)
* Examined precision and recall to understand error trade-offs
* Selected the best model + threshold combination based on validation performance

---

## Submission
* Trained the final model on the full training dataset
* Generated predictions for the test set
* Created submission file in the required format:
---

## Key Concepts Explored

* Click-through prediction in **recommendation systems**
* Feature engineering from user behavior and context
* Linear vs tree-based vs ensemble models
* Threshold tuning for accuracy-driven competitions
* End-to-end Kaggle-style ML workflow

---

## Tools & Libraries
* Python
* NumPy, Pandas
* Scikit-learn
* (Optional) XGBoost / LightGBM
* Matplotlib / Seaborn

---

## Key Learnings
This project strengthened understanding of **applied machine learning in competitive settings**, particularly model comparison, feature engineering, and accuracy-focused optimization on large-scale tabular data.

---
