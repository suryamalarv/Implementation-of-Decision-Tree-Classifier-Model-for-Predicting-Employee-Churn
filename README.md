# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import pandas module and import the required data set.
2.Find the null values and count them.
3.Count number of left values.
4.From sklearn import LabelEncoder to convert string values to numerical values.
5.From sklearn.model_selection import train_test_split.
6.Assign the train dataset and test dataset.
7.From sklearn.tree import DecisionTreeClassifier.
8.Use criteria as entropy.
9.From sklearn import metrics.
10.Find the accuracy of our model and predict the require values.
## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: SURYAMALARV
RegisterNumber:  212223230224
*/

import pandas as pd
data = pd.read_csv("Employee.csv")
print(data.head())
```
![image](https://github.com/user-attachments/assets/ca6f285f-9e58-4faa-8aa4-389ee511cbfe)

```
data.info()
```
![image](https://github.com/user-attachments/assets/1944cfd8-e622-47fd-ad8c-0f65560b707e)
```
data.isnull().sum()
```
![image](https://github.com/user-attachments/assets/899f2bbd-5fc8-40a8-b9bb-13a96c5a8cbe)
```
data["left"].value_counts()
```
![image](https://github.com/user-attachments/assets/c7509eb0-276f-4887-82cd-a22a1de05370)
```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()
```
![image](https://github.com/user-attachments/assets/46c13a68-6fb5-4b7f-a6cd-29c34da70563)
```
x=data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","Work_accident","promotion_last_5years","salary"]]
x.head()
```
![image](https://github.com/user-attachments/assets/289121f9-5fb2-4dbe-85b4-155e7bb89ffb)
```
y=data["left"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=1)
from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```
![image](https://github.com/user-attachments/assets/076202d1-66e1-4cdf-bb36-0d808fe492a7)
```
dt.predict([[0.5,0.8,9,260,6,0,1,]])
```
![image](https://github.com/user-attachments/assets/8306fb49-ddff-4f2f-ac38-cc7d95b0598a)
![image](https://github.com/user-attachments/assets/2637d025-f925-4195-be0e-17a3e34a3bdd)


## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
