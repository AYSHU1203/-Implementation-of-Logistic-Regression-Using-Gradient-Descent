# Implementation-of-Logistic-Regression-Using-Gradient-Descent

## AIM:
To write a program to implement the the Logistic Regression Using Gradient Descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the required libraries.

2.Load the dataset and print the values.

3.Define X and Y array and display the value.

4.Find the value for cost and gradient.

5.Plot the decision boundary and predict the Regression value.

## Program:
Program to implement the the Logistic Regression Using Gradient Descent.

Developed by: AYSHWARIYA.J

RegisterNumber: 212224230030
```Python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
dataset = pd.read_csv('Placement_Data.csv')
dataset
dataset = dataset.drop('sl_no',axis=1)
dataset = dataset.drop('salary',axis=1)
dataset["gender"] = dataset["gender"].astype('category')
dataset["ssc_b"] = dataset["ssc_b"].astype('category')
dataset["hsc_b"] = dataset["hsc_b"].astype('category')
dataset["degree_t"] = dataset["degree_t"].astype('category')
dataset["workex"] = dataset["workex"].astype('category')
dataset["specialisation"] = dataset["specialisation"].astype('category')
dataset["status"] = dataset["status"].astype('category')
dataset["hsc_s"] = dataset["hsc_s"].astype('category')
dataset.dtypes
dataset["gender"] = dataset["gender"].cat.codes
dataset["ssc_b"] = dataset["ssc_b"].cat.codes
dataset["hsc_b"] = dataset["hsc_b"].cat.codes
dataset["degree_t"] = dataset["degree_t"].cat.codes
dataset["workex"] = dataset["workex"].cat.codes
dataset["specialisation"] = dataset["specialisation"].cat.codes
dataset["status"] = dataset["status"].cat.codes
dataset["hsc_s"] = dataset["hsc_s"].cat.codes
dataset
X = dataset.iloc[:, :-1].values
Y = dataset.iloc[:,-1].values
Y
theta = np.random.randn(X.shape[1])
y=Y
def sigmoid(z):
  return 1 / (1 + np.exp(-z))
def gradient_descent(theta, X, y, alpha, num_iterations):
  m = len(y)
  for i in range(num_iterations):
    h = sigmoid(X.dot(theta))
    gradient = X.T.dot(h - y) / m
    theta -= alpha * gradient
  return theta
theta = gradient_descent(theta, X, y, alpha=0.01, num_iterations=1000)
def predict(theta, X):
  h = sigmoid(X.dot(theta))
  y_pred = np.where(h >= 0.5,1, 0)
  return y_pred
y_pred = predict(theta, X)
accuracy = np.mean(y_pred.flatten() == y)
print("Accuracy", accuracy)
print(y_pred)
print(Y)
xnew = np.array([[0, 87, 0, 95, 0, 2, 78, 2, 0, 0, 1, 0]])
y_prednew = predict (theta, xnew)
print(y_prednew)
xnew = np.array([[0, 0, 0, 0, 0, 2, 8, 2, 0, 0, 1, 0]])
y_prednew = predict (theta, xnew)
print(y_prednew)
```


## Output:
Dataset

![Image-1](https://github.com/user-attachments/assets/fc10e48f-3bf2-424f-9426-8b31cc128824)

![Image-2](https://github.com/user-attachments/assets/a677f17e-9360-485c-a7c6-e2f562c2365f)
![Image-3](https://github.com/user-attachments/assets/c2841c93-42a4-4392-94da-6984f983621a)
![Image-4](https://github.com/user-attachments/assets/0254f4e9-b62e-414c-baed-fbf917150f3f)

Accuracy and Predicted Values

![Image-8](https://github.com/user-attachments/assets/6201a5d8-bafe-4653-9a6f-104b94547bf9)
![Image-5](https://github.com/user-attachments/assets/19a8278e-34cd-4394-9fa4-863049cf850d)
![Image-6](https://github.com/user-attachments/assets/636845be-bf05-4356-b2c2-79f2111f28a3)
![Image-7](https://github.com/user-attachments/assets/26afe363-6265-4d4f-8675-e83757bb435c)








## Result:
Thus the program to implement the the Logistic Regression Using Gradient Descent is written and verified using python programming.

