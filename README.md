# 🌟 Airbnb Superhost Analysis in Houston

## 🧾 Project Overview

This project focuses on **predicting Superhost status** and **estimating revenue uplift** for Airbnb listings in **Houston** using data from 2016 to 2018. The study combines **exploratory analysis**, **hypothesis testing**, and **machine learning** to help Airbnb optimize host engagement strategies, maximize Superhost retention, and boost overall platform revenue.

## 👥 Team

**MGMT 68700 – AI for Business Decisions**  
**Group 15**: Hrishikesh Bhatt, Namra Shah

---

## 📌 Business Objectives

- Predict which hosts will **gain or lose Superhost status** in future evaluations.
- Quantify **revenue uplift** attributable to Superhost status.
- Recommend actionable strategies to:
  - **Retain existing Superhosts**
  - **Promote capable non-Superhosts**
  - **Enhance host performance and guest satisfaction**

---

## 📊 Dataset

- **Source**: Airbnb Houston data across 8 quarterly evaluation periods (Jul 2016 – Apr 2018)
- **Size**: 118,677 listings, 111 features, 11,797 unique hosts
- **Structure**: Each row = listing performance in a quarterly window

### Key Feature Categories:

- **Host performance metrics** (e.g., ratings, reviews, cancellations)
- **Reservation & booking behavior** (e.g., booked days, average price)
- **Environmental variables** (e.g., tract_superhosts_ratio, listing_type)
- **Target variables**: Superhost status & revenue estimation

---

## 🔍 Methodology

### 📈 Exploratory Data Analysis (EDA)

- **Imputation**: Median (interval vars), Mode (categorical vars)
- **Transformations**: Log transformation to reduce skew
- **Balancing**: Applied **SMOTE** to address class imbalance

### 💰 Revenue Modeling

- Calculated revenue:  
  `estimated_revenue = booked_days × booked_days_avePrice`

- Conducted hypothesis test (t-test):
  - **Result**: Superhosts earn **significantly more** (p < 0.000)
  - **Model**: Random Forest Regressor  
    - MAE = 1.262  
    - MSE = 5.941

### 🧠 Superhost Prediction

- **Model**: Logistic Regression  
  - AUC (test) = **0.975**  
  - High specificity (97%), moderate sensitivity (82%)

- **Model output**:
  - 1,881 predicted to **lose** Superhost status
  - 821 predicted to **gain** Superhost status
  - ~13k listings correctly predicted to maintain status

- **Key positive predictors**:
  - Previous Superhost status
  - High average rating
  - High tract Superhost ratio

- **Key negative predictors**:
  - High number of cancellations
  - Large number of reviews (often correlated with negative feedback)

---

## 📌 Insights & Recommendations

### 📍 Factors aligned with Airbnb's criteria:

| Metric                     | Business Interpretation |
|---------------------------|-------------------------|
| `numReservedDays_pastYear` | Indicator of experience |
| `rating_ave_pastYear`      | Reflects responsiveness |
| `numCancel_pastYear`       | Shows host reliability |
| `prop_5_StarReviews_pastYear` | Captures guest satisfaction |
| `available_days`           | Reflects availability & potential revenue |

### 🧠 Suggested Interventions

- **For at-risk Superhosts**:
  - Offer cancellation insurance, training programs
  - Leverage automation tools for responsiveness

- **For promising non-Superhosts**:
  - Promote availability and visibility in competitive tracts
  - Suggest pricing strategies and review optimization

- **Platform-wide**:
  - Use model insights to **target incentives**
  - Monitor **local market dynamics** for customized support
  - Emphasize **data-driven host engagement**

---

## 🛠️ Tools & Technologies

- Python (pandas, statsmodels, scikit-learn)
- Data preprocessing (log transform, imputation, SMOTE)
- Hypothesis testing (t-test)
- Machine Learning: Logistic Regression, Random Forest Regressor
- Data visualization (EDA charts, maps)

---

## 📈 Final Outcome

- Validated that **Superhost status drives higher revenue**
- Built a robust predictive model (AUC = 0.975) to forecast host status
- Generated **strategic levers** for Airbnb to:
  - Improve host retention
  - Drive more listings to Superhost tier
  - Maximize user experience and platform revenue

---

> _"Superhost status isn’t just a badge—it’s a signal of excellence. With the right insights, Airbnb can nurture more Superhosts and elevate the platform for hosts and guests alike."_
