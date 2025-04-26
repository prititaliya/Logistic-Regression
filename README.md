# Logistic Regression and Perceptron Trick — My Work

---

## 🚀 What I Was Trying to Do

In this project, I was trying to build logistic regression manually from scratch and understand:
- How to classify linearly separable data.
- How perceptron learning works to draw the correct line.
- Why we need a **learning rate** to prevent overshooting.
- How logistic regression compares with a simple perceptron.

---

## 📚 Important Concepts I Learned

### 1. **Logistic Regression - Why It Is Useful**
- Simple, interpretable, efficient for binary classification.
- Provides probability scores instead of just class labels.
- Works very well when data is **linearly separable** (can separate with one straight line).

> Logistic Regression assumes **data should be linearly classifiable**.

---

### 2. **Perceptron Trick - How We Move The Line**

When we have two classes and want to separate them, we can think like:
- A line is drawn initially.
- **If a point is wrongly classified**, we adjust the line slightly.

The adjustment depends on what we want:
- **Changing intercept (C):** Moves the line **up** or **down** **parallelly**.
- **Changing slope (A or B):** **Tilts the line** around the axes.

💬 In simple words:
- If the intercept **C** increases → the line goes **down**.
- If the intercept **C** decreases → the line goes **up**.
- If the coefficient **A** or **B** changes → the line **rotates**.

> **We make very small changes** to the line to fix wrong predictions **without making the line jump too much**.

---

### 3. **Learning Rate - Why It Is Critical**

If we don't use a learning rate, and directly update the weights:
- The line moves **too much**.
- Model becomes unstable and **may overshoot** the correct position.

By using a **small learning rate** (like 0.1):
- Each update is **small**.
- The line **slowly adjusts** towards correct separation.
- This prevents **drastic changes** and **makes training stable**.

**Learning rate idea**:
```math
new_weight = old_weight + learning_rate * (y_true - y_predicted) * input
```
---
from sklearn.linear_model import LogisticRegression

logreg = LogisticRegression()
logreg.fit(X, y)
m1 = logreg.coef_[0][0]
c1 = logreg.intercept_[0]

plt.figure(figsize=(10, 5))
plt.scatter(X[:, 0], X[:, 1], c=y, s=25, edgecolor='k')
plt.plot(X[:, 0], m*X[:, 0] + c, color='green', label="Perceptron Boundary")
plt.plot(X[:, 0], m1*X[:, 0] + c1, color='red', label="Logistic Regression Boundary")
plt.legend()
plt.show()
