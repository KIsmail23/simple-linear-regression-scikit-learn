# Simple-linear-regression-scikit-learn
A simple implementation of Linear Regression using Scikit-Learn with synthetic data. The project demonstrates model training, prediction, visualization, and evaluation using MSE and R² metrics.

# Simple Linear Regression with Scikit-Learn

This repository contains a simple example of **Linear Regression** using **Scikit-Learn**.  
The model is trained on synthetic data, and predictions are visualized along with performance metrics.

---

## 📌 Features
- Generate synthetic dataset
- Train a Linear Regression model
- Visualize actual vs. predicted values
- Evaluate model using **MSE** and **R² score**

---

## 📂 Project Structure

import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, r2_score
import matplotlib.pyplot as plt

# Generate synthetic data
np.random.seed(42)
X = np.random.rand(100, 1) * 100
y = 3 * X + np.random.randn(100, 1) * 2

# Split Data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Fit Linear Regression
model = LinearRegression()
model.fit(X_train, y_train)

# Make Predictions
y_pred = model.predict(X_test)

# Print coefficients
print("Slope : ", model.coef_[0][0])
print("Intercept : ", model.intercept_[0])

plt.scatter(X_test, y_test, color="blue", label="Actual")
plt.plot(X_test, y_pred, color="red", label="Predicted")
plt.title("Linear Regression Model")
plt.xlabel("X")
plt.ylabel("y")
plt.legend()
plt.show()

# Evaluate performance
mse = mean_squared_error(y_test, y_pred)
r2 = r2_score(y_test, y_pred)
print("MSE: ", mse)
print("R-Squared: ", r2)


<img width="640" height="480" alt="Figure_1" src="https://github.com/user-attachments/assets/3313b894-c11e-400c-a15e-7888676edd1e" />



