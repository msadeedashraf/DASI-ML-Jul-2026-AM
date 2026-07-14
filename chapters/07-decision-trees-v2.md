# 07 — Decision Trees (Learning Through Questions)

## 🎯 Learning Objectives

By the end of this chapter you should be able to:

- Explain how Decision Trees work.
- Identify the parts of a Decision Tree.
- Understand how Decision Trees make predictions.
- Build a Decision Tree model using scikit-learn.
- Describe common real-world applications.

---

# 🌍 Why This Chapter Matters

Many everyday decisions follow a sequence of questions.

Examples:

- Can I get a loan?
- Does a patient have a disease?
- Should a customer receive a discount?
- Should an email be marked as spam?

Decision Trees work the same way by asking a series of questions until a final decision is reached.

---

# 💡 What is a Decision Tree?

A Decision Tree is a Machine Learning algorithm that makes predictions by following a series of **if-else style questions**.

Each answer moves to another branch until a final prediction is made.

---

# 🌳 Parts of a Decision Tree

- Root Node – First question
- Branch – Possible answers
- Internal Node – Additional questions
- Leaf Node – Final prediction

---

# 📊 Visual Mental Model

```text
Study Hours > 2.5?
        │
   ┌────┴────┐
  Yes       No
   │         │
 Pass      Fail
```

---

# 🌎 Real-World Applications

- Loan approval
- Medical diagnosis
- Fraud detection
- Customer segmentation
- Product recommendations
- Quality inspection
- Employee hiring

---

# 💻 Python Example

```python
import pandas as pd
from sklearn.tree import DecisionTreeClassifier

data = pd.DataFrame({
    "hours":[1,2,3,4,5],
    "result":[0,0,1,1,1]
})

X=data[["hours"]]
y=data["result"]

model=DecisionTreeClassifier(max_depth=3)

model.fit(X,y)

print(model.predict([[6]]))
```

---

# ⚠️ Common Beginner Mistakes

- Creating trees that are too deep.
- Forgetting to limit tree depth.
- Assuming Decision Trees always give the best model.
- Forgetting double brackets for features.

---

# 🎤 Interview Corner

**Question:** Why are Decision Trees easy to explain?

**Answer:** Because every prediction follows a sequence of understandable questions.

---

# 📌 One-Minute Revision

- Decision Trees learn rules.
- They ask questions one step at a time.
- Root → Branch → Leaf.
- Deep trees may overfit.

---

# 📚 Chapter Summary

Decision Trees are one of the easiest Machine Learning algorithms to understand because they closely resemble human decision-making. They are widely used in finance, healthcare, retail, and many business applications.
