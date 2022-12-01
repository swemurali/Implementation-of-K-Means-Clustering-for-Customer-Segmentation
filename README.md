# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
1.Import pandas and matplot libraries.
2.import Kmeans algorithm to solve customer segmentation.
3.Using the for loop cluster the given data
4.Predict the output and plot data graphs.
5.Display the outputs
```
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: M.Suwetha
RegisterNumber:  212221230112
*/
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wess=[]
for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wess.append(kmeans.inertia_)
plt.plot(range(1,11),wess);
plt.xlabel("no of clusters")
plt.ylabel("wess")
plt.title("elbow method")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income"],df0["Score"],c="red",label="cluster0")
plt.scatter(df1["Annual Income"],df1["Score"],c="black",label="cluster1")
plt.scatter(df2["Annual Income"],df2["Score"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income"],df3["Score"],c="green",label="cluster3")
plt.scatter(df4["Annual Income"],df4["Score"],c="red",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
### DATA.INFO()
![Screenshot 2022-11-10 144100](https://user-images.githubusercontent.com/94165336/201089862-429f9d37-57f8-45a4-acda-d734cab8fb41.png)
### DATA.HEAD()
![Screenshot 2022-11-10 144152](https://user-images.githubusercontent.com/94165336/201090024-7c5e5cbc-19d8-4d6c-b246-9b703434de42.png)
### initial dataset
![k1](https://user-images.githubusercontent.com/94165336/204975865-3a352add-3469-4d5d-a99d-088336ebc64c.png)
### null values
![k2](https://user-images.githubusercontent.com/94165336/204975935-751563af-d516-4194-918f-db5698565b18.png)
![k3](https://user-images.githubusercontent.com/94165336/204975944-ad696b8f-eec7-4213-8fc5-0280d43a3072.png)
### elbow graph
![k4](https://user-images.githubusercontent.com/94165336/204976001-0ec631ba-ab42-491b-a0e2-80d347af0068.png)
### clusters
![k5](https://user-images.githubusercontent.com/94165336/204976081-039d34c9-801f-4e67-8617-d08faaafc273.png)
### y predict array
![k6](https://user-images.githubusercontent.com/94165336/204976174-77b5c93b-3663-4023-9bac-d09aa91da569.png)
### customer segmentation
![k7](https://user-images.githubusercontent.com/94165336/204976216-665dcebd-428e-4e52-a8fb-024b549a8df9.png)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
