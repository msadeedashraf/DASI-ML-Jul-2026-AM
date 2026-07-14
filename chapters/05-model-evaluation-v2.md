# 05 — Model Evaluation (How Good Is Your Machine Learning Model?)

## 🎯 Learning Objectives

By the end of this chapter you should be able to:

- Explain why model evaluation is important.
- Compare actual values with predicted values.
- Describe MAE, MSE, and Accuracy.
- Select the correct evaluation metric for Regression and Classification.
- Evaluate a simple Machine Learning model using scikit-learn.

---

# 🌍 Why This Chapter Matters

Imagine buying a GPS that is wrong by 2 km every time.

Or a weather app that predicts sunshine while it rains.

A Machine Learning model is only useful if its predictions are reliable.

Model Evaluation helps us measure **how good** a model really is.

---

# 💡 What is Model Evaluation?

Model Evaluation is the process of measuring how well a trained model performs on unseen data.

It compares:

**Actual Values** vs **Predicted Values**

Smaller errors generally indicate a better model.

---

# 📊 Regression vs Classification Metrics

| Problem Type | Common Metrics |
|--------------|----------------|
| Regression | MAE, MSE |
| Classification | Accuracy |

---

# 🧠 Mean Absolute Error (MAE)

MAE calculates the average difference between predictions and actual values.

Lower MAE = Better model.

---

# 🧠 Mean Squared Error (MSE)

MSE squares the errors before averaging them.

Large mistakes are penalized more heavily.

Lower MSE = Better model.

---

# 🧠 Accuracy

Accuracy measures the percentage of correct predictions.

Higher Accuracy = Better model.

---

# 🌎 Real-World Applications

- Weather forecasting
- House price prediction
- Fraud detection
- Student performance prediction
- Medical diagnosis
- Sales forecasting

---

# 💻 Python Example

```python
from sklearn.metrics import mean_absolute_error, mean_squared_error

actual = [50,60,70,80]
predicted = [52,59,68,82]

print("MAE:", mean_absolute_error(actual,predicted))
print("MSE:", mean_squared_error(actual,predicted))
```

Classification example:

```python
from sklearn.metrics import accuracy_score

actual=[1,0,1,1]
predicted=[1,0,0,1]

print("Accuracy:", accuracy_score(actual,predicted))
```

---

# ⚠️ Common Beginner Mistakes

- Evaluating only the training data.
- Thinking 100% accuracy is always possible.
- Using Accuracy for Regression.
- Using MAE for Classification.

---

# 🎤 Interview Corner

**Question:** Which metric would you use for predicting house prices?

**Answer:** MAE or MSE because house prices are continuous numeric values.

---

# 📌 One-Minute Revision

- Evaluate every model.
- Regression → MAE, MSE.
- Classification → Accuracy.
- Compare actual and predicted values.

---

# 📚 Chapter Summary

Model Evaluation tells us whether a Machine Learning model performs well enough to be trusted. Choosing the correct metric depends on whether the problem is Regression or Classification.
