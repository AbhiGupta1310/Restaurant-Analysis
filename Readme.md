# 🍽️ Restaurant Rating Prediction - ML Project

This project focuses on predicting restaurant ratings using structured data, with a complete end-to-end machine learning pipeline — from data cleaning and feature engineering to model evaluation and interpretation.

---

## 🚀 Overview

The goal is to build a **predictive and interpretable model** that estimates restaurant ratings based on features like cost, cuisine, location, and popularity metrics. The project demonstrates how raw data can be transformed into **actionable business intelligence** for restaurant discovery, recommendation engines, and decision support systems.

---

## 🎯 Objectives

- Predict aggregate ratings of restaurants using regression models.
- Extract and visualize insights about the drivers behind high or low ratings.
- Handle multi-label fields, missing values, and skewed distributions.

---

## 📦 Dataset

The dataset includes:
- **Categorical features**: City, Restaurant Type, Online delivery status, Cuisine(s)
- **Numerical features**: Cost for two, Votes, Aggregate Rating
- **Location-based tiers**: Tier 1, 2, and 3 cities derived for generalization

> 📌 *Note: Raw dataset is not included due to licensing.*

---

## 🧹 Data Preprocessing & Feature Engineering

- One-hot encoded multi-labeled features (like `Cuisines`)
- Binned cost values and tiered city categorization
- Handled missing values using logical imputations
- Applied log transformation to handle skewness in fields like `Votes`
- Removed low-frequency and noisy categorical data

---

## 📊 Exploratory Data Analysis (EDA)

- ANOVA tests to validate significant features
- Box plots and correlation heatmaps to analyze trends
- Found that mid-priced restaurants in Tier 1 cities often score higher
- Cuisine groupings like "North Indian + Mughlai" showed higher rating tendencies

---

## 🤖 Model Building & Evaluation

Several regression models were explored to find the best performer:

| Model                      | Key Observation | Outcome |
|---------------------------|-----------------|---------|
| **Linear Regression**     | Good baseline, poor fit on non-linear patterns | Underfit |
| **Decision Tree Regressor** | Captured non-linearity well but overfitted | High variance |
| **Random Forest Regressor** | Improved generalization, good feature ranking | Solid performer |
| **Gradient Boosting Regressor (GBR)** | Best results, good control on overfitting | ✅ Final choice |

**Final Model: Gradient Boosting Regressor (GBR)**  
- **R² Score ≈ 0.75** on validation set  
- Tuned using **GridSearchCV** with cross-validation  
- Feature importance and **Partial Dependence Plots (PDPs)** used for explainability

---

## ⚙️ Challenges Tackled

- ✅ Multi-label and sparse categorical fields
- ✅ Skewed distributions (votes, cost)
- ✅ Missing values and unbalanced city distribution
- ✅ Overfitting in tree-based models

---

## 📈 Insights & Impact

- Cuisines, cost bracket, and city tier are major drivers of ratings.
- Discovered that **highly rated, underpriced restaurants** exist in Tier 2 cities — great for recommender systems.
- The pipeline is easily adaptable for deployment in recommendation engines or data dashboards.

---

## 🔮 Future Improvements

- Integrate NLP-based sentiment scores from user reviews
- Convert the pipeline into a Flask/Streamlit web app
- Include model monitoring metrics in production deployment

---

## 🗂️ Project Structure

