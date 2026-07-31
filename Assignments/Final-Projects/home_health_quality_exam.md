# 📘 Final Individual Project — Machine Learning (Classification + Regression)

## 🏥 Dataset: CMS Home Health Provider Quality Dataset

---

## 🎯 Objective

You are working individually as a **data analyst for a healthcare-quality organization**.

Your goal is to:

> Analyze home-health provider performance, build predictive models, compare their results, and recommend ways to improve patient-care quality.

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
- Present your final healthcare-quality recommendations.

---

## ⚠️ Project Requirements

- Complete both the regression and classification sections.
- Build and compare at least two regression models.
- Build and compare at least two classification models.
- Explain why each model was selected.
- Use `random_state` when splitting data and when supported by the model.
- Do not use identifier or contact columns as model features.
- Do not use footnote columns as model features.
- Prevent target leakage by following the feature-exclusion instructions in each modelling task.

---

# 🧠 SECTION 1 — DATA UNDERSTANDING AND PREPARATION

## Task 1 — Dataset Overview

- Display the number of rows and columns.
- List all column names.
- Explain what the main groups of columns represent:
  - Provider identification and location
  - Type of ownership
  - Services offered
  - Patient-care measures
  - Hospital and emergency-care measures
  - Medicare spending
  - Footnotes
- Identify numerical, categorical, Boolean, identifier, and text-description columns.
- Identify the target used for regression and the target that will be created for classification.

## Task 2 — Data Quality and Cleaning

- Check for missing values in every column.
- Check for duplicate rows.
- Check the data type of every column.
- Identify columns that contain only one value.
- Identify columns that are completely empty.
- Examine missing values in `Quality of Patient Care Star Rating`.
- Remove or exclude rows with a missing star rating before building the models.
- Remove or exclude identifier, contact, and footnote columns from modelling.
- Apply only additional cleaning supported by your findings.
- Explain why each cleaning decision is necessary.

## Task 3 — Feature Engineering

Create these two new features using the corresponding patient-care columns:

### `average_mobility_improvement`

Calculate the average of:

- `How often patients got better at walking or moving around`
- `How often patients got better at getting in and out of bed`
- `How often patients got better at bathing`

### `average_unplanned_care`

Calculate the average of:

- `How often home health patients had to be admitted to the hospital`
- `How often patients receiving home health care needed urgent, unplanned care in the ER without being admitted`

For each new feature:

- Show the code used to create it.
- Explain what it represents.
- Explain why it may help analyze provider quality.

---

# 📊 SECTION 2 — EXPLORATORY DATA ANALYSIS

## Task 4 — Star Rating Distribution

- Count providers in each `Quality of Patient Care Star Rating` category.
- Calculate the percentage in each rating category.
- Create a suitable visualization.
- Explain what the distribution tells you about provider quality.

## Task 5 — Ownership and State Analysis

- Count providers by `Type of Ownership`.
- Calculate the average star rating for each ownership type.
- Identify states with the highest and lowest average star ratings.
- Include the number of rated providers when comparing states.
- Create at least one suitable visualization.
- Explain the business meaning of your findings.

## Task 6 — Patient Outcomes and Star Ratings

- Compare `average_mobility_improvement` across star-rating categories.
- Compare `average_unplanned_care` across star-rating categories.
- Create suitable visualizations.
- Explain whether higher-rated providers appear to have better patient outcomes.

---

# 📈 SECTION 3 — REGRESSION

## Task 7 — Prepare the Regression Data

Use `Quality of Patient Care Star Rating` as the regression target.

- Select suitable patient-care, hospital-use, ownership, and state features.
- Do not use the star-rating target as an input feature.
- Do not use any classification target derived from the star rating.
- Exclude `index`, `CMS Certification Number (CCN)*`, `Provider Name`, `Address`, `City`, `Zip`, `Phone`, `Date Certified`, and all footnote columns.
- Handle missing values in the selected features using a method covered in class.
- Convert selected categorical features into numerical form when needed.
- Split the data into training and testing sets.
- Explain why the selected features may help predict the star rating.

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

Create a new target named `high_quality`:

- `1` when `Quality of Patient Care Star Rating >= 4.0`
- `0` when `Quality of Patient Care Star Rating < 4.0`

Create this target only after removing rows with missing star ratings.

Then:

- Display the number and percentage of providers in each class.
- Select suitable patient-care, hospital-use, ownership, and state features.
- Do not use `Quality of Patient Care Star Rating` or `high_quality` as input features.
- Apply the same identifier, contact, date, and footnote exclusions used in regression.
- Handle missing values in the selected features using a method covered in class.
- Convert selected categorical features into numerical form when needed.
- Split the data into training and testing sets.
- Explain why this is a classification problem.

## Task 11 — Train Two Classification Models

Train both:

- `LogisticRegression`
- `DecisionTreeClassifier`

For each model:

- Fit the model using the training data.
- Predict the provider-quality class for the test data.
- Briefly explain why the model is being tested.

## Task 12 — Evaluate and Compare the Classification Models

For both classification models:

- Calculate accuracy.
- Display the confusion matrix.
- Explain true positives, true negatives, false positives, and false negatives in the context of identifying high-quality providers.

Create a comparison table:

| Model | Accuracy | Strength | Weakness |
|---|---:|---|---|

- Identify which classifier performed better.
- Support your decision using the required evaluation results.

## Task 13 — Prediction Probability

Using the logistic regression model:

- Use `predict_proba()` on the test data.
- Display the predicted probability of being a high-quality provider for at least five providers.
- Compare each probability with its predicted class and actual class.
- Explain in your own words what the predicted probability means.

---

# ⚖️ SECTION 5 — INTERPRETATION, IMPROVEMENT, AND RECOMMENDATIONS

## Task 14 — Feature Importance and Model Improvement

- Use the decision tree classifier to identify the most important features for predicting `high_quality`.
- Display the most important features in a table or visualization.
- Explain what the top features suggest about provider quality.
- Improve one model by adding or removing features, or by tuning a model setting already covered in class.
- Re-evaluate it using the same metric or metrics used before.
- State whether the change improved the model.

## Task 15 — Final Decision, Recommendations, and Reflection

Write a clear final conclusion that answers all of the following:

- Which regression model would you choose, and why?
- Which classification model would you choose, and why?
- Which patient-care measures appear most connected to provider quality?
- What patterns did you find across ownership types or states?
- Give at least three practical quality-improvement recommendations supported by your analysis.
- What limitations should be considered before using these models to evaluate a healthcare provider?
- What did you learn from completing this project?

---

## ✅ Final Submission Checklist

- [ ] All 15 tasks are completed.
- [ ] Notebook code runs from beginning to end.
- [ ] Required outputs and visualizations are visible.
- [ ] Written interpretations are included.
- [ ] Regression models are compared using MAE and R².
- [ ] Classification models are compared using accuracy and confusion matrices.
- [ ] Missing star ratings are removed before creating `high_quality`.
- [ ] Identifier, contact, date, and footnote columns are excluded from modelling.
- [ ] Target leakage is prevented.
- [ ] Final recommendations are supported by results from the dataset.
- [ ] The work was completed and explained individually.
