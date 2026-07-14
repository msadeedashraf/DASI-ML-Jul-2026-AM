# 06 — K-Nearest Neighbors (KNN)

## 🎯 Learning Objectives

By the end of this chapter you should be able to:

- Explain how KNN works.
- Describe the role of the value **k**.
- Differentiate KNN Classification and KNN Regression.
- Build a KNN model using scikit-learn.
- Understand when KNN is a good choice.

---

# 🌍 Why This Chapter Matters

Many real-world decisions are made by comparing similar cases.

Examples:

- Netflix recommends movies watched by people with similar interests.
- Amazon recommends products bought by similar customers.
- Doctors compare patients with similar symptoms.
- Banks compare customers with similar financial histories.

KNN follows the same idea:

**Look at the closest examples and let them guide the prediction.**

---

# 💡 What is KNN?

KNN stands for **K-Nearest Neighbors**.

Instead of learning a mathematical formula, KNN stores the training data.

When new data arrives, KNN finds the **k closest neighbors** and makes a prediction based on them.

---

# 🧠 What Does 'k' Mean?

k = Number of neighbors considered.

Examples:

- k = 1
- k = 3
- k = 5

Choosing the right value of k is important.

---

# 📊 Visual Mental Model

```text
New Student
      │
      ▼
Find Closest Students
      │
      ▼
Majority Vote
      │
      ▼
Prediction
```

---

# 🌎 Real-World Applications

- Movie recommendations
- Product recommendations
- Medical diagnosis
- Fraud detection
- Customer segmentation
- Image recognition
- Similar document search

---

# 💻 Python Example

```python
import pandas as pd
from sklearn.neighbors import KNeighborsClassifier

data = pd.DataFrame({
    "hours":[1,2,3,4,5],
    "result":[0,0,1,1,1]
})

X=data[["hours"]]
y=data["result"]

model=KNeighborsClassifier(n_neighbors=3)

model.fit(X,y)

print(model.predict([[6]]))
```

---

# ⚠️ Common Beginner Mistakes

- Choosing k that is too small.
- Choosing k that is too large.
- Forgetting feature scaling for KNN.
- Thinking KNN creates equations.

---

# 🎤 Interview Corner

**Question:** What does KNN stand for?

**Answer:** K-Nearest Neighbors. It predicts using the closest training examples.

---

# 📌 One-Minute Revision

- KNN compares similar examples.
- k is the number of neighbors.
- Small k may overfit.
- Large k may underfit.
- KNN works for both Classification and Regression.

---

# 📚 Chapter Summary

KNN is a simple yet powerful algorithm that predicts by comparing new data with similar historical examples. It is widely used in recommendation systems, pattern recognition, and classification tasks.
