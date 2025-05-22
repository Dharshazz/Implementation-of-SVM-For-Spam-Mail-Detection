# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary python packages using import statements.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Split the dataset using train_test_split.

4.Calculate Y_Pred and accuracy.

5.Print all the outputs.

6.End the Program.

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: M GAYATHIRI ROSHINI 
RegisterNumber: 212223110012
*/
import chardet
file='spam.csv'
with open (file,'rb') as rawdata:
    result = chardet.detect(rawdata.read(100000))
result
import pandas as pd
data=pd.read_csv("spam.csv",encoding='windows-1252')
data.head()
```

## Output:
![image](https://github.com/user-attachments/assets/2e95e245-d0eb-42b2-8fc9-0c45fa1c7fd1)
```
data.info()
```
![image](https://github.com/user-attachments/assets/33fc8833-8a50-4d86-a240-a26c9c4e432f)
```
data.isnull().sum()
```
![image](https://github.com/user-attachments/assets/c206dcac-10bb-467a-aa14-b7a14ede32b8)
```
x=data["v1"].values
y=data["v2"].values
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)
from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()
x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred
```
![image](https://github.com/user-attachments/assets/e2682c60-6224-42d1-a974-2c62ee6dde87)

```
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```
![image](https://github.com/user-attachments/assets/1cdbac53-92f8-4d97-a9b1-c7008d64761e)


## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
