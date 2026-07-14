# 03 — Classification (Predicting Categories with Machine Learning)

## 🎯 Learning Objectives
- Explain Classification.
- Distinguish Classification from Regression.
- Identify binary and multi-class problems.
- Build a Logistic Regression classifier.
- Interpret predictions and probabilities.

---

# 🌍 Why This Chapter Matters

Classification predicts **categories**, not numbers.

Examples:
- Spam / Not Spam
- Pass / Fail
- Fraud / Legitimate
- Approved / Rejected

---

# 💡 What is Classification?

Classification predicts labels.

Rule of thumb:

**If the answer belongs to a category, use Classification.**

---

# 🤔 Regression vs Classification

| Regression | Classification |
|------------|----------------|
| Numbers | Categories |
| House Price | Spam / Not Spam |
| Salary | Pass / Fail |

---

# 🌎 Real-World Applications

- Spam filtering
- Fraud detection
- Loan approval
- Medical diagnosis
- Customer churn
- Face recognition
- Product purchase prediction

---

# 💻 Python Example

```python
import pandas as pd
from sklearn.linear_model import LogisticRegression

data = pd.DataFrame({
    "hours":[1,2,3,4,5],
    "result":[0,0,1,1,1]
})

X = data[["hours"]]
y = data["result"]

model = LogisticRegression()
model.fit(X,y)

print(model.predict([[6]]))
print(model.predict_proba([[6]]))
```

---

# ⚠️ Common Beginner Mistakes

- Using Regression for categories.
- Confusing probability with prediction.
- Forgetting double brackets for X.

---

# 🎤 Interview Corner

When should Classification be used?

Answer: When the target belongs to predefined categories.

---

# 📌 Summary

Classification predicts categories such as Yes/No, Pass/Fail and Spam/Not Spam using patterns learned from historical data.
