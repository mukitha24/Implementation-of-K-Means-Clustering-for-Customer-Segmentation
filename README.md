# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the output and end the program. 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: MUKITHA V M
RegisterNumber:  212223040119
*/

import numpy as np
import pandas as pd

import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range (1,11):
kmeans=KMeans(n_clusters = i,init="k-means++")
kmeans.fit(data.iloc[:,3:])
wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow matter")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-
100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-
100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-
100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-
100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-
100)"],c="magenta",label="cluster4")

plt.legend()
plt.title("Customer Segmets")

```

## Output:
## DATASET
![282252079-d40d7994-05c8-4fc8-a325-1c155027e8cc](https://github.com/user-attachments/assets/998a1a24-40dd-42e4-9ffa-904c84ba13b7)
## Data.head()
![282252124-deb74fb4-afb0-418a-83ca-0ecfa11f11b1](https://github.com/user-attachments/assets/668e7a92-6779-444d-b216-8a34a3233843)
## Data.info()
![282252165-2c77531a-5348-4721-a1ca-253d0e0fe4ac](https://github.com/user-attachments/assets/10f9def4-f30c-4cae-8025-c3d032fe39ed)
## data.isnull() & sum()
![282252218-f8479871-7b6b-48ba-b213-c8d10444439f](https://github.com/user-attachments/assets/4df9a5e2-0e2d-4b94-a1a9-7ba7982ca543)
## Elbow method graph
![282252254-2eb45380-b82a-4564-9e80-ee5823d0c3d3](https://github.com/user-attachments/assets/6de83c88-52f0-40a4-837b-f0b502bd8414)
## K means cluster
![282252281-d618eb9d-0dda-4109-82cd-bf2260450359](https://github.com/user-attachments/assets/85679129-00f7-4889-9883-7a7821bbfd61)
## Y prediction value
![Screenshot 2024-11-04 154108](https://github.com/user-attachments/assets/f260b6bd-1e2c-49a0-8571-6efc93aa8c36)
## Customers Segments Graph:
![Screenshot 2024-11-04 154214](https://github.com/user-attachments/assets/62800048-8466-4b35-958d-3d6a2a17498a)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
