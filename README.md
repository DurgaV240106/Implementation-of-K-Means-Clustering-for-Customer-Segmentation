# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Data Preparation: Load data, handle missing values, and extract relevant features for clustering.
2.Determine Clusters: Use the Elbow Method to find optimal number of clusters based on WCSS.
3.K-Means Clustering: Fit the K-Means model with optimal clusters, predict cluster labels for data. 
4.Visualization: Plot data points with distinct colors for each cluster to visualize clustering results.
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: DURGA V
RegisterNumber: 212223230052 
*/
```
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: AVINASH T
RegisterNumber: 212223230026
import pandas as pd 
import matplotlib.pyplot as plt 
data=pd.read_csv("Mall_Customers.csv")
data.head()
```
## Output:
![image](https://github.com/user-attachments/assets/50f8411d-9125-49d5-957f-0a1fe3d0d97c)

```
data.info()
```
![image](https://github.com/user-attachments/assets/019b4f40-f0fb-460b-96b7-d9db1f0047ca)

```
data.isnull().sum()
```
![image](https://github.com/user-attachments/assets/811f2be6-7194-4da4-b116-9f257aa10c18)

```
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No.of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
```
![image](https://github.com/user-attachments/assets/7c383538-625e-4d9d-8abe-a4b76907b472)
```
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
KMeans(n_clusters=5)
y_pred=km.predict(data.iloc[:,3:])
y_pred
```
![image](https://github.com/user-attachments/assets/e2539368-27e4-4941-adc1-0cca2859a2db)
```
data["cluster"]=y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"], color = "gold")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"], color = "pink")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"], color = "green")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"], color = "blue")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"], color = "red")
plt.show()
```
![image](https://github.com/user-attachments/assets/3db3f40b-a888-40ba-b9a3-a1a42773f736)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
