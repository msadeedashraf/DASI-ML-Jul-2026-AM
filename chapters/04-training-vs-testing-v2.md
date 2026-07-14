# 04 — Training vs Testing (How Machine Learning Models Learn)

## 🎯 Learning Objectives

By the end of this chapter you should be able to:

- Explain why datasets are split into training and testing sets.
- Describe the purpose of training and testing data.
- Explain overfitting in simple terms.
- Use `train_test_split()` in scikit-learn.
- Build and test a simple regression model.

---

# 🌍 Why This Chapter Matters

Imagine a student memorizes every answer from a practice test.

On the practice test they score **100%**.

On the real exam they score **52%**.

Did the student actually learn?

**No. They memorized.**

Machine Learning models can make exactly the same mistake.

That is why we split our data into **Training** and **Testing** sets.

---

# 💡 What is Training Data?

Training data is the portion of the dataset used to teach the model.

The model studies patterns from this data.

Example:

Hours Studied → Exam Score

---

# 💡 What is Testing Data?

Testing data is **new data** the model has never seen before.

It is used to answer one question:

> Can the model make good predictions on unseen data?

---

# 📊 Visual Mental Model

```text
Complete Dataset
        │
        ▼
 ------------------------
| Training |  Testing   |
|   80%    |    20%     |
 ------------------------
        │
        ▼
 Train Model
        │
        ▼
 Test Model
        │
        ▼
 Evaluate Performance
```

---

# 🌎 Real-World Examples

- Schools use past student records to predict future grades.
- Banks train on historical transactions and test on new ones.
- Hospitals train on previous patient records and evaluate on new patients.
- Online stores train on old purchases and recommend products to new customers.
- Weather agencies train on historical weather and predict tomorrow's forecast.

---

# 💻 Fully Commented Python Example

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression

data = pd.DataFrame({
    "hours":[1,2,3,4,5,6,7,8],
    "score":[50,55,65,70,80,85,90,95]
})

X = data[["hours"]]
y = data["score"]

X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=1
)

model = LinearRegression()

model.fit(X_train, y_train)

predictions = model.predict(X_test)

print(predictions)
```

---

# ⚠️ Common Beginner Mistakes

- Training and testing on the same data.
- Forgetting `random_state`.
- Believing 100% training accuracy means a good model.
- Using an extremely small testing set.

---

# 🎤 Interview Corner

**Question:** Why do we split data into training and testing sets?

**Answer:** To measure how well the model performs on unseen data rather than the data it memorized.

---

# 📌 One-Minute Revision

- Training teaches the model.
- Testing evaluates the model.
- Unseen data gives a realistic measure of performance.
- A common split is 80% training and 20% testing.

---

# 📚 Chapter Summary

Training helps the model learn patterns from historical data, while testing checks whether those patterns generalize to new data. Splitting the dataset is one of the most important practices in Machine Learning because it helps prevent overfitting and provides a fair evaluation of model performance.
