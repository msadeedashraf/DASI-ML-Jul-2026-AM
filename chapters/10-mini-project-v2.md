# 10 — Mini Project (End-to-End Machine Learning Project)

## 🎯 Learning Objectives

By the end of this chapter you should be able to:

- Apply the complete Machine Learning workflow.
- Import and explore a dataset.
- Prepare features and target.
- Split data into training and testing sets.
- Train a model.
- Evaluate the model.
- Make predictions on new data.

---

# 🌍 Project Scenario

You have been hired by a real estate company to help estimate house prices.

Your task is to build a Machine Learning model that predicts the selling price of a house based on historical data.

---

# 🪜 Machine Learning Workflow

```text
Business Problem
      │
      ▼
Collect Data
      │
      ▼
Clean Data
      │
      ▼
Feature Engineering
      │
      ▼
Train/Test Split
      │
      ▼
Train Model
      │
      ▼
Evaluate Model
      │
      ▼
Predict New Data
```

---

# 📂 Sample Dataset

| Size | Bedrooms | Age | Price |
|-----:|----------:|----:|------:|
|1200|2|20|450000|
|1600|3|10|590000|
|2000|4|5|760000|

Features:
- Size
- Bedrooms
- Age

Target:
- Price

---

# 💻 Complete Python Example

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_absolute_error

data = pd.DataFrame({
    "size":[1200,1600,2000,2200,2600],
    "bedrooms":[2,3,4,4,5],
    "age":[20,10,5,8,2],
    "price":[450000,590000,760000,790000,920000]
})

X = data[["size","bedrooms","age"]]
y = data["price"]

X_train,X_test,y_train,y_test = train_test_split(
    X,y,test_size=0.2,random_state=1
)

model = LinearRegression()
model.fit(X_train,y_train)

predictions = model.predict(X_test)

print("MAE:", mean_absolute_error(y_test,predictions))

new_house = [[1800,3,7]]
print("Predicted Price:", model.predict(new_house))
```

---

# 🌎 Other Mini Project Ideas

- Student exam score prediction
- Taxi fare prediction
- Ice cream sales prediction
- Customer churn prediction
- Loan approval prediction

---

# ⚠️ Common Beginner Mistakes

- Skipping data cleaning.
- Training on all the data.
- Forgetting model evaluation.
- Predicting before training.

---

# 🎤 Interview Corner

**Question:** What are the major steps in a Machine Learning project?

**Answer:** Define the problem, collect data, prepare the data, split it, train the model, evaluate it, and make predictions.

---

# 📌 One-Minute Revision

- Start with a business problem.
- Prepare clean data.
- Split into training/testing.
- Train the model.
- Evaluate the model.
- Predict new data.

---

# 📚 Chapter Summary

This mini project combines everything learned throughout the course into one end-to-end workflow. Completing projects like this builds confidence and demonstrates practical Machine Learning skills.
