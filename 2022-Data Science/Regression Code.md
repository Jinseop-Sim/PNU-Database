# Regression Code
---
## Simple Linear Regression
- Make Data
```python
import pandas as pd
data = pd.read_csv("https://raw.githubusercontent.com/inetguru/IDS-CB35533/blob/main/diabetes.csv")
data.head()

# Data from http://github.com/integuru, PNU professor Jong duck Kim
# Class from PNU Data Science, by Professor Myeon ho Lee
```

- Linear Regression
```python
from sklearn import linear_model
predictor = ['BMI']
target = ['Y']
train_data = data[:420]
test_data = data[421:442]

X = train_data[predictor]
Y = train_data[target]
X_test = test_data[predictor]
Y_test = test_data[target]

reg = linear_model.LinearRegression()
reg.fit(X, Y)

print("Slope = ", reg.coef_, "Intercept = ", reg.intercept_) # Slope & Intercept
print("Predicted Y with BMI = 28.5, y_hat = ", reg.predict[[28.5]])

reg.score() # R^2 Score = SSR/SST = (SST-SSE) / SST

# Base Code from,
# Class from PNU Data Science, by Professor Myeon ho Lee
```

## Multi-Variable Simple Linear Regression
- Linear Regression
```python
from sklearn import linear_model
predictor = ['BMI', 'BP']
target = ['Y']
train_data = data[:420]
test_data = data[421:442]

X = train_data[predictor]
Y = train_data[target]
X_test = test_data[predictor]
Y_test = test_data[target]

reg = linear_model.LinearRegression()
reg.fit(X, Y)

print("Slope = ", reg.coef_, "Intercept = ", reg.intercept_) # Slope & Intercept
print("Predicted Y with BMI = 28.5, BP = 100.0 y_hat = ", reg.predict[[28.5, 100.0]])

reg.score() # R^2 Score = SSR/SST = (SST-SSE) / SST

# Base Code from,
# Class from PNU Data Science, by Professor Myeon ho Lee
```

## Logistic Regression
- Make Data
```python
import numpy as np
import pandas as pd
from sklearn import linear_model
from sklearn import metrics
from sklearn.model_selection import train_test_split
import seaborn as sn
import matplotlib.pyplot as plt

data = pd.read_csv('https://raw.githubusercontent.com/inetguru/IDS-CB35533/main/pima_diabetes.csv')

train_data, test_data = train_test_split(data, train_size=0.8, random_state=1)

# Data from http://github.com/integuru, PNU professor Jong duck Kim
# Class from PNU Data Science, by Professor Myeon ho Lee
```

- Logistic Regression
```python
predictor = ['Glucose']
target = 'Outcome'

X = train_data[predictor]
Y = train_data[target]
X_test = test_data[predictor]
Y_test = test_data[target]

reg = linear_model.LogisticRegression()
reg.fit(X, Y)
print("Slope = ", reg.coef_, "Intercept = ", reg.intercept_) # Slope & Intercept

Y_pred = reg.predict(X_test) # Predict with Test data
confusion_matrix = pd.crosstab(Y_test, Y_pred, rownames=["Actual"], colnames=["Predicted"])
sn.heatmap(confusion_matrix, annot=True) 
plt.show() # Show confusion Matrix

print("Accuracy : ", metrics.accuracy_score(Y_test, Y_pred)) # Accuracy = TP + TN / TP+FP+TN+FN

# Base Code from,
# Class from PNU Data Science, by Professor Myeon ho Lee
```

## Multi-Variable Logistic Regression
- Logistic Regression
```python
predictor = ['Pregnancies', 'Glucose', 'Insulin']
target = 'Outcome'

X = train_data[predictor]
Y = train_data[target]
X_test = test_data[predictor]
Y_test = test_data[target]

reg = linear_model.LogisticRegression()
reg.fit(X, Y)
print("Slope = ", reg.coef_, "Intercept = ", reg.intercept_) # Slope & Intercept

Y_pred = reg.predict(X_test) # Predict with Test data
Single_pred = reg.predict([[10, 150, 10]]) # Single Predictation with Pregnancies = 10, Glucose = 150, Insulin = 10.
print(Single_pred)

confusion_matrix = pd.crosstab(Y_test, Y_pred, rownames=["Actual"], colnames=["Predicted"])
sn.heatmap(confusion_matrix, annot=True) 
plt.show() # Show confusion Matrix

print("Accuracy : ", metrics.accuracy_score(Y_test, Y_pred)) # Accuracy = TP + TN / TP+FP+TN+FN

# Base Code from,
# Class from PNU Data Science, by Professor Myeon ho Lee
```
