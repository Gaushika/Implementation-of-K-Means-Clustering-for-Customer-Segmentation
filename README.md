# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
Step1: Import the necessary packages using import statement.
Step2: Read the given csv file using read_csv() method and print the number of contents to be
displayed using df.head().
Step3: Import KMeans and use for loop to cluster the data.
Step4: Predict the cluster and plot data graphs.
Step5: Print the outputs and end the program

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Gaushika RR 
RegisterNumber: 212225040091
*/

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss= []
for i in range(1,11):
    kmeans=KMeaans(n_clusters = i,init = "k-means++", random_state=42)
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
plt.show()
km=KMeans(n_clusters = 5, init = "k-means++", random_state=42)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.figure(figsize=(10, 8))
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="black",label="Cluster 0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="cyan",label="Cluster 1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="yellow",label="Cluster 2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="Cluster 3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="green",label="Cluster 4")
plt.legend()
plt.title("Customer Segments")
plt.xlabel("Annual Income (k$)")
plt.ylabel("Spending Score (1-100)")
plt.show()
```

## Output:
<img width="956" height="676" alt="{76B21061-E2EA-4D17-8056-289D55EE6E5C}" src="https://github.com/user-attachments/assets/c384c7f2-bc8d-46fe-898a-488ba4b71a25" />
<img width="995" height="736" alt="{D84393FD-6621-4A3F-9BD8-285813E647FB}" src="https://github.com/user-attachments/assets/b5d32029-3353-413e-9d15-43a0e3ca10d4" />


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
