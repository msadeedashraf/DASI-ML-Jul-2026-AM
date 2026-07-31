# 📘 Final Individual Project — Machine Learning (Classification + Regression)

## 💳 Dataset: Credit Card Fraud Transactions

---

## 🎯 Objective

You are working individually as a **data analyst for a financial institution**.

Your goal is to:

> Explore transaction patterns, build regression and classification models, compare their performance, and recommend ways to improve fraud detection.

This is a **single-person project**. You must complete and explain every part of the work yourself.

---

## 📦 Deliverables

### 1. Jupyter Notebook (`.ipynb`)

- Organize the notebook using the 15 task headings below.
- Include clean and readable code.
- Show all required tables, plots, predictions, and evaluation results.
- Add a short written interpretation after each result.

### 2. Final Report (`.pdf` or `.docx`)

- Summarize the main findings from all 15 tasks.
- Include the most useful visualizations.
- Compare the models clearly.
- Present your final fraud-detection recommendations.

---

## ⚠️ Project Requirements

- Complete both the regression and classification sections.
- Build and compare at least two regression models.
- Build and compare at least two classification models.
- Explain why each model was selected.
- Use `random_state` when splitting data and when supported by the model.
- Do not use `transaction_id` as a model feature.
- Do not use `is_fraud` when predicting `merchant_risk_score`.
- Do not use `merchant_risk_score` as an input feature when predicting `is_fraud`.

---

# 🧠 SECTION 1 — DATA UNDERSTANDING AND PREPARATION

## Task 1 — Dataset Overview

- Display the number of rows and columns.
- List all column names.
- Explain what each column represents.
- Identify the numerical and categorical columns.
- State whether the dataset contains any true free-text column.
- Identify the target columns that will be used for regression and classification.

## Task 2 — Data Quality and Cleaning

- Check for missing values in every column.
- Check for duplicate rows.
- Check the data type of every column.
- Inspect the values in `is_fraud` and confirm that it is a binary target.
- Apply only the cleaning that is supported by your findings.
- Explain why each cleaning decision is necessary. If no cleaning is required, support that conclusion with evidence.

## Task 3 — Feature Engineering

Create these two new features:

- `amount_to_balance_ratio` = `amount_usd / account_balance_usd`
- `is_night_transaction` = 1 when `time_of_day_hour` is from 0 through 5; otherwise 0

For each feature:

- Show the code used to create it.
- Explain what it represents.
- Explain why it may be useful for analyzing transaction risk.

---

# 📊 SECTION 2 — EXPLORATORY DATA ANALYSIS

## Task 4 — Fraud Distribution

- Count fraudulent and non-fraudulent transactions.
- Calculate the percentage of each class.
- Create a suitable visualization.
- Explain what the distribution tells you about the dataset.

## Task 5 — Transaction Amount and Fraud

- Compare `amount_usd` for fraudulent and non-fraudulent transactions.
- Calculate an appropriate summary, such as the mean or median for each class.
- Create a visualization of the comparison.
- Explain the pattern you observe.

## Task 6 — Categorical Fraud Analysis

Analyze fraud using all three of these columns:

- `merchant_category`
- `channel`
- `auth_method`

For each column:

- Calculate the fraud count or fraud rate by category.
- Create at least one suitable visualization across this task.
- Identify the categories associated with the highest fraud levels.
- Explain the possible business meaning of your findings.

---

# 📈 SECTION 3 — REGRESSION

## Task 7 — Prepare the Regression Data

Use `merchant_risk_score` as the regression target.

- Select suitable features from the dataset.
- Exclude `transaction_id`, `merchant_risk_score`, and `is_fraud` from the input features.
- Convert categorical features into a numerical form when needed.
- Split the data into training and testing sets.
- Explain why the selected features may help predict merchant risk.

## Task 8 — Train Two Regression Models

Train both:

- `LinearRegression`
- `DecisionTreeRegressor`

For each model:

- Fit the model using the training data.
- Make predictions using the test data.
- Briefly explain why the model is being tested.

## Task 9 — Evaluate and Compare the Regression Models

Evaluate both regression models using:

- Mean Absolute Error (`MAE`)
- R² score

Create a comparison table containing:

| Model | MAE | R² | Strength | Weakness |
|---|---:|---:|---|---|

- Identify the better regression model.
- Support your decision using the evaluation results.

---

# 🧠 SECTION 4 — CLASSIFICATION

## Task 10 — Prepare the Classification Data

Use the existing `is_fraud` column as the classification target:

- `1` = fraudulent transaction
- `0` = non-fraudulent transaction

Then:

- Select suitable input features.
- Exclude `transaction_id`, `is_fraud`, and `merchant_risk_score` from the input features.
- Convert categorical features into a numerical form when needed.
- Split the data into training and testing sets.
- Explain why this is a classification problem.

## Task 11 — Train Two Classification Models

Train both:

- `LogisticRegression`
- `DecisionTreeClassifier`

For each model:

- Fit the model using the training data.
- Predict the fraud class for the test data.
- Briefly explain why the model is being tested.

## Task 12 — Evaluate and Compare the Classification Models

For both classification models:

- Calculate accuracy.
- Display the confusion matrix.
- Explain true positives, true negatives, false positives, and false negatives in the context of fraud detection.

Create a comparison table:

| Model | Accuracy | Strength | Weakness |
|---|---:|---|---|

- Identify which classifier performed better based on the required results.
- Explain why accuracy alone may give an incomplete picture when one class is much smaller than the other.

## Task 13 — Prediction Probability

Using the logistic regression model:

- Use `predict_proba()` on the test data.
- Display the predicted probability of fraud for at least five transactions.
- Compare each probability with its predicted class and actual class.
- Explain in your own words what a fraud probability means.

---

# ⚖️ SECTION 5 — INTERPRETATION, IMPROVEMENT, AND RECOMMENDATIONS

## Task 14 — Feature Importance and Model Improvement

- Use the decision tree model to identify the most important features for fraud prediction.
- Display the most important features in a table or visualization.
- Explain what the top features suggest about fraudulent transactions.
- Improve one model by adding or removing features, or by tuning a model setting already covered in class.
- Re-evaluate it using the same metric or metrics used before.
- State whether the change improved the model.

## Task 15 — Final Decision, Recommendations, and Reflection

Write a clear final conclusion that answers all of the following:

- Which regression model would you choose, and why?
- Which classification model would you choose for fraud detection, and why?
- What transaction patterns should the financial institution monitor?
- Give at least three practical fraud-detection recommendations supported by your analysis.
- What did you learn from completing this project?

---

## ✅ Final Submission Checklist

- [ ] All 15 tasks are completed.
- [ ] Notebook code runs from beginning to end.
- [ ] Required outputs and visualizations are visible.
- [ ] Written interpretations are included.
- [ ] Regression models are compared using MAE and R².
- [ ] Classification models are compared using accuracy and confusion matrices.
- [ ] Final recommendations are supported by results from the dataset.
- [ ] The work was completed and explained individually.
