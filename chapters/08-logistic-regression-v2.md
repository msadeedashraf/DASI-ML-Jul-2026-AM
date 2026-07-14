# 08 — Logistic Regression (Predicting Probability)

## 🎯 Learning Objectives

By the end of this chapter you should be able to:

- Explain Logistic Regression.
- Understand why it is a Classification algorithm.
- Interpret probabilities produced by the model.
- Understand the decision threshold.
- Build a Logistic Regression model using scikit-learn.

---

# 🌍 Why This Chapter Matters

Many business decisions are based on probability rather than certainty.

Examples:

- What is the probability a customer will buy?
- What is the probability an email is spam?
- What is the probability a patient has a disease?
- What is the probability a loan will default?

Logistic Regression answers these questions.

---

# 💡 What is Logistic Regression?

Logistic Regression is a **Classification** algorithm.

It predicts a **probability** between 0 and 1.

That probability is then converted into a category.

Example:

Probability = 0.92

Prediction = Pass

---

# 🧠 Decision Threshold

Most Logistic Regression models use:

Probability ≥ 0.5 → Class 1

Probability < 0.5 → Class 0

---

# 📊 Visual Mental Model

```text
Features
    │
    ▼
Probability
    │
    ▼
Decision
```

---

# 🌎 Real-World Applications

- Spam detection
- Disease prediction
- Loan approval
- Customer churn
- Product purchase prediction
- Fraud detection
- Insurance risk assessment

---

# 💻 Python Example

```python
import pandas as pd
from sklearn.linear_model import LogisticRegression

data = pd.DataFrame({
    "hours":[1,2,3,4,5],
    "result":[0,0,1,1,1]
})

X=data[["hours"]]
y=data["result"]

model=LogisticRegression()

model.fit(X,y)

print(model.predict([[6]]))
print(model.predict_proba([[6]]))
```

---

# ⚠️ Common Beginner Mistakes

- Thinking Logistic Regression predicts numbers.
- Ignoring prediction probabilities.
- Confusing Regression with Logistic Regression.
- Forgetting double brackets.

---

# 🎤 Interview Corner

**Question:** Why is Logistic Regression a Classification algorithm?

**Answer:** Because the final output is a category, even though it predicts a probability first.

---

# 📌 One-Minute Revision

- Logistic Regression predicts probabilities.
- Probabilities become categories.
- Threshold commonly equals 0.5.
- Used for binary Classification.

---

# 📚 Chapter Summary

Logistic Regression predicts the probability of belonging to a class and converts that probability into a category. It is one of the most widely used Classification algorithms in Machine Learning.
