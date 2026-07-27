# Machine Learning Challenge Exercises

These exercises are designed to help students apply regression, classification,
feature engineering, model evaluation, and data exploration skills using the
provided synthetic datasets.

## Datasets
- `make_student_success()`
- `make_housing()`
- `make_netflix()`
- `make_healthcare()`
- `make_fraud()`

---

# Student Success (Classification)

```python
X, y = make_student_success()
```

### Challenge 1 – Explore the Data

```python
print(X.head())
print(X.info())
print(X.describe())
print(y[:10])
```

Questions:
1. How many features are there?
2. Which feature has the largest range?
3. Which feature might be the most important?

### Challenge 2 – Filter Data

Display students with:
- Hours > 8
- Attendance > 90
- Sleep > 7

### Challenge 3 – Feature Engineering

Create:

```
study_score = hours * attendance
```

Discuss whether it may improve predictions.

### Challenge 4 – Remove a Feature

Remove `practice_tests`, retrain the model, and compare the accuracy.

### Challenge 5 – Increase Noise

Increase the noise from `0.07` to `0.25`.

How does this affect accuracy?

---

# Housing Prices (Regression)

```python
X, y = make_housing()
```

### Challenge 1

Find the largest and smallest house.

### Challenge 2

Combine `X` and `y` into one DataFrame and calculate the average price by city.

### Challenge 3

Remove the `city` feature and retrain the model.

### Challenge 4 – Feature Engineering

Create:

```
price_per_bed = price / beds
```

Would it be useful?

### Challenge 5

Predict the price of:
- 1500 sqft
- 3 bedrooms
- Toronto

Repeat for Calgary.

Explain the difference.

---

# Netflix Dataset

```python
(Xr, yr), (Xc, yc) = make_netflix()
```

### Challenge 1

Which dataset is regression and which is classification?

### Challenge 2 – Feature Engineering

Create:

```
engagement = clicks * watch_minutes
```

Would this create data leakage?

### Challenge 3

Compare average watch time on weekdays versus weekends.

### Challenge 4

Investigate users with `watch_minutes > 140`.

### Challenge 5

Compare Linear Regression and Decision Tree Regression using MAE and MSE.

---

# Healthcare (Classification)

```python
X, y = make_healthcare()
```

### Challenge 1

Display patients older than 70.

### Challenge 2

Count patients with oxygen below 94.

### Challenge 3 – Feature Engineering

Create a `fever_level` category using `pd.cut()`.

### Challenge 4

Which feature appears to be the most important?

### Challenge 5

Remove the oxygen feature and compare the new model.

---

# Fraud Detection (Classification)

```python
X, y = make_fraud()
```

### Challenge 1

Calculate the fraud percentage.

### Challenge 2

Explain why a model with 98% accuracy may still be poor.

### Challenge 3

Find all transactions with:
- Amount > 100
- International = 1
- Night = 1

### Challenge 4 – Feature Engineering

Create:

```
risk_score = amount * is_international
```

### Challenge 5

Find:
- Largest legitimate transaction
- Smallest fraudulent transaction

Discuss why they exist.

---

# Cross-Dataset Challenges

## Challenge 1

For every dataset determine:
1. Regression or Classification?
2. Best algorithm?
3. Best evaluation metric?

## Challenge 2

Rank the features from most useful to least useful.

Compare your ranking with:

```python
model.feature_importances_
```

## Challenge 3

Introduce missing values, clean the data, retrain, and compare results.

## Challenge 4

Compare three algorithms:
- Linear/Logistic Regression
- KNN
- Decision Tree

Record your results in a comparison table.

---