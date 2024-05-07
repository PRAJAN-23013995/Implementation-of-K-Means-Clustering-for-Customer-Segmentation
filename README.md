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

5.Print the outputs and end the program 
    

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: PRAJAN P
RegisterNumber: 212223240121
*/

import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No.of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

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
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
  
```

## Output:
Data head():
![278858717-21ec9e1a-063b-41f3-89e0-4448b05b1403](https://github.com/PRAJAN-23013995/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150313345/7ce001c5-dac5-4dcb-88bc-569c10dc1af5)

Data.info():
![278859011-99cce45e-1d31-4b58-aadb-4e7e232a0124](https://github.com/PRAJAN-23013995/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150313345/9843daa2-02c6-4944-a1bb-71822981b66d)

Data.isnull().sum() function:

Elbow method graph:
![278859129-7b9d6077-6dff-4792-a6f6-577c384d4ab7](https://github.com/PRAJAN-23013995/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150313345/1622c353-8dc7-4f09-a714-bc2113a3d4c8)

K mean clusters:
![278859151-fb551b02-8440-47a5-96ed-ef757fe0b87f](https://github.com/PRAJAN-23013995/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150313345/c7e4bf17-c101-47da-a50b-7a17607819b0)

Y_prediction:
![278859213-f70fca1e-ddbd-46d7-b7e2-30510c302825](https://github.com/PRAJAN-23013995/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150313345/93961300-e26e-42ed-9d0b-88958d0a582f)

Customer Segments Graph:
![278859231-a57174c0-a293-494f-84d0-079c2ced8120](https://github.com/PRAJAN-23013995/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150313345/3e00e1f8-a796-4130-a217-2d29cddd386c)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
