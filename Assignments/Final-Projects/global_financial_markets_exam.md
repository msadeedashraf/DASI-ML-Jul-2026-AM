# 📘 Final Individual Project — Machine Learning (Classification + Regression)

## 📈 Dataset: Global Financial Markets Dataset

---

## 🎯 Objective

You are working individually as a **data analyst for a financial-services company**.

Your goal is to:

> Explore global market data, build regression and classification models, compare their performance, and provide evidence-based market insights.

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
- Present your final recommendations.

---

## ⚠️ Project Requirements

- Complete both the regression and classification sections.
- Build and compare at least two regression models.
- Build and compare at least two classification models.
- Explain why each model was selected.
- Use `random_state` when splitting data and when supported by the model.
- Do not use a feature when it directly reveals the target.
- Do not treat `symbol`, `asset_name`, `asset_type`, or `region` as free-text review data.

---

# 🧠 SECTION 1 — DATA UNDERSTANDING AND PREPARATION

## Task 1 — Dataset Overview

- Display the number of rows and columns.
- List all column names.
- Explain what each column represents.
- Identify the numerical and categorical columns.
- State whether the dataset contains any true free-text column.
- Display the earliest and latest values in `date`.
- Identify the targets that will be used for regression and classification.

## Task 2 — Data Quality and Cleaning

- Check for missing values in every column.
- Check for duplicate rows.
- Check the data type of every column.
- Check whether `high` is normally greater than or equal to `open`, `close`, and `low`.
- Check whether `low` is normally less than or equal to `open`, `close`, and `high`.
- Investigate rows with a `volume` of zero before deciding whether they should be changed or removed.
- Apply only cleaning supported by your findings.
- Explain every cleaning decision. If no change is made, support that decision with evidence.

## Task 3 — Feature Engineering

Create these three new features:

- `daily_range` = `high - low`
- `price_change` = `close - open`
- `percentage_change` = `((close - open) / open) * 100`

For each feature:

- Show the code used to create it.
- Explain what it represents.
- Explain how it may help analyze daily market performance.

---

# 📊 SECTION 2 — EXPLORATORY DATA ANALYSIS

## Task 4 — Asset Distribution

- Count the records for each `asset_type`.
- Count the number of unique `symbol` values in each asset type.
- Create a suitable visualization.
- Explain what the distribution tells you about the dataset.
- Examine `region` and explain whether it is useful for comparing records in this dataset.

## Task 5 — Daily Price Movement Analysis

- Compare the number of records with a positive, negative, or zero `price_change`.
- Calculate the average `price_change` and `percentage_change` for each `asset_type`.
- Create a suitable visualization.
- Explain the patterns you observe.

## Task 6 — Asset and Volume Analysis

- Identify the assets with the highest average `daily_range`.
- Compare average `volume` across `asset_type`.
- Identify which assets contain the most zero-volume records.
- Create at least one suitable visualization.
- Explain the business meaning of your findings.

---

# 📈 SECTION 3 — REGRESSION

## Task 7 — Prepare the Regression Data

Use `close` as the regression target.

- Select suitable input features from the dataset.
- Do not use `close`, `price_change`, or `percentage_change` as input features.
- Convert categorical features into numerical form when needed.
- Split the data into training and testing sets.
- Explain why the selected features may help predict the closing price.

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

Create a comparison table:

| Model | MAE | R² | Strength | Weakness |
|---|---:|---:|---|---|

- Identify the better regression model.
- Support your decision using the evaluation results.

---

# 🧠 SECTION 4 — CLASSIFICATION

## Task 10 — Create and Prepare the Classification Target

Create a new target named `price_increased`:

- `1` when `close >= open`
- `0` when `close < open`

Then:

- Display the number and percentage of records in each class.
- Select suitable input features.
- Do not use `close`, `price_change`, `percentage_change`, or `price_increased` as input features.
- Convert categorical features into numerical form when needed.
- Split the data into training and testing sets.
- Explain why this is a classification problem.

## Task 11 — Train Two Classification Models

Train both:

- `LogisticRegression`
- `DecisionTreeClassifier`

For each model:

- Fit the model using the training data.
- Predict the price-movement class for the test data.
- Briefly explain why the model is being tested.

## Task 12 — Evaluate and Compare the Classification Models

For both classification models:

- Calculate accuracy.
- Display the confusion matrix.
- Explain true positives, true negatives, false positives, and false negatives in the context of predicting daily price direction.

Create a comparison table:

| Model | Accuracy | Strength | Weakness |
|---|---:|---|---|

- Identify which classification model performed better.
- Support your decision using the required evaluation results.

## Task 13 — Prediction Probability

Using the logistic regression model:

- Use `predict_proba()` on the test data.
- Display the predicted probability of a price increase for at least five records.
- Compare each probability with its predicted class and actual class.
- Explain in your own words what the predicted probability means.

---

# ⚖️ SECTION 5 — INTERPRETATION, IMPROVEMENT, AND RECOMMENDATIONS

## Task 14 — Feature Importance and Model Improvement

- Use the decision tree classifier to identify the most important features for predicting `price_increased`.
- Display the most important features in a table or visualization.
- Explain what the top features suggest about daily price direction.
- Improve one model by adding or removing features, or by tuning a model setting already covered in class.
- Re-evaluate the model using the same metric or metrics used before.
- State whether the change improved the model.

## Task 15 — Final Decision, Recommendations, and Reflection

Write a clear final conclusion that answers all of the following:

- Which regression model would you choose, and why?
- Which classification model would you choose, and why?
- Which asset types or assets showed the most notable price or volume patterns?
- Give at least three practical recommendations supported by your analysis.
- What limitations should be considered before using these models for real financial decisions?
- What did you learn from completing this project?

---

## ✅ Final Submission Checklist

- [ ] All 15 tasks are completed.
- [ ] Notebook code runs from beginning to end.
- [ ] Required outputs and visualizations are visible.
- [ ] Written interpretations are included.
- [ ] Regression models are compared using MAE and R².
- [ ] Classification models are compared using accuracy and confusion matrices.
- [ ] Target-derived columns are excluded from model inputs.
- [ ] Final recommendations are supported by results from the dataset.
- [ ] The work was completed and explained individually.
