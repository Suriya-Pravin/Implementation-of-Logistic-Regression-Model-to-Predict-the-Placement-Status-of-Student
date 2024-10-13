### Date:
# Ex-5:Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required packages and print the present data.
2. Print the placement data and salary data.
3. Find the null and duplicate values.
4. Using logistic regression find the predicted values of accuracy , confusion matrices.
5. Display the results.

## Program and Output:
```
/*
Program to implement the the Logistic Regression Model
to Predict the Placement Status of Student.

Developed by: Suriya Pravin M
RegisterNumber: 212223230223
*/
```

```
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression

dataset = pd.read_csv('Placement_Data_Full_Class.csv')
dataset.head()
```
![1)](https://github.com/user-attachments/assets/28f569d9-120a-441d-8631-474e00160078)

```
dataset.info()
```
![2)](https://github.com/user-attachments/assets/d6bf008a-6195-4d4e-9723-383432b76fbd)

```
dataset = dataset.drop('sl_no', axis=1);
dataset.info()
```
![3)](https://github.com/user-attachments/assets/7875751b-37ee-448d-975c-7bdc096cb316)
```
dataset["gender"] = dataset["gender"].astype('category')
dataset["ssc_b"] = dataset["ssc_b"].astype('category')
dataset["hsc_b"] = dataset["hsc_b"].astype('category')
dataset["degree_t"] = dataset["degree_t"].astype('category')
dataset["workex"] = dataset["workex"].astype('category')
dataset["specialisation"] = dataset["specialisation"].astype('category')
dataset["status"] = dataset["status"].astype('category')
dataset["hsc_s"] = dataset["hsc_s"].astype('category')
dataset.dtypes
```
![4)](https://github.com/user-attachments/assets/624bc7b6-de38-49f8-bab5-d7945c5afd70)
```
dataset["gender"]=dataset["gender"].cat.codes
dataset["ssc_b"]=dataset["ssc_b"].cat.codes
dataset["hsc_b"]=dataset["hsc_b"].cat.codes
dataset["degree_t"]=dataset["degree_t"].cat.codes
dataset["workex"]=dataset["workex"].cat.codes
dataset["specialisation"]=dataset["specialisation"].cat.codes
dataset["status"]=dataset["status"].cat.codes
dataset["hsc_s"]=dataset["hsc_s"].cat.codes
dataset

```
![5)](https://github.com/user-attachments/assets/4dc74614-1d8f-4986-9ce8-f4dd394869e8)

```
x = dataset.iloc[:,:-1]
x
```
![6)](https://github.com/user-attachments/assets/d263c04b-61c4-4d0a-8663-6c031bccd575)

```
y=dataset.iloc[:,-1]
y
```
![7)](https://github.com/user-attachments/assets/a74256f5-2e82-4a58-aeeb-fdc3ed3f21c4)

```
x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.2, random_state=0)
clf = LogisticRegression()
clf.fit(x_train, y_train)
y_pred=clf.predict(x_test)
y_pred
```
![8)](https://github.com/user-attachments/assets/6deb0b42-b036-48fb-ad2f-dc687a73c57e)

```
from sklearn.metrics import accuracy_score, confusion_matrix
cf = confusion_matrix(y_test, y_pred)
cf
```
![9)](https://github.com/user-attachments/assets/f21c0bf8-ff9b-458f-8cb0-79a566141415)

```
accuracy=accuracy_score(y_test,y_pred)
accuracy
```
![10)](https://github.com/user-attachments/assets/144b4d0f-6787-439b-8994-0fb1ec0fa256)

## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
