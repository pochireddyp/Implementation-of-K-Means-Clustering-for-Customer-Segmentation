# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Start the program
   
2.Import the necessary python libraries

3.Read the dataset of Mall_Customers csv file

4.From sklearn libraary select the cluster and import KMeans Clustering

5.Find the sum of squared distance between each points and the centroid in a cluster using Elbow Method

6.Plot the graph x and y as Number of Clusters and wcss respectively

7.Using the matplotlib library draw the scatter plot for the given number of clusters (ie. here n_clusters = 5)

8.Stop the program


## Program:
```p

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: pochi reddy.p
RegisterNumber: 212223240115
```

```p
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
```
```p
data.head()
```

```p
data.info()
```

```p
data.isnull().sum()
```

```p
from sklearn.cluster import KMeans
wcss = []
```

```p
for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
```

```p
plt.plot(range(1,11),wcss)
plt.xlabel("No . of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")
```

```p
km=KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
```

```p
y_pred = km.predict(data.iloc[:,3:])
y_pred
```

```p
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments   ")
```

## Output:

![image](https://github.com/pochireddyp/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150232043/e2ba8949-9d1e-4237-aad5-6e812c5c1d55)

![image](https://github.com/pochireddyp/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150232043/b55d935d-ca48-4b60-8771-5d204eacfe61)

![image](https://github.com/pochireddyp/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150232043/3494ea58-228b-428e-a10d-732133e72a70)

![image](https://github.com/pochireddyp/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150232043/008e640e-fa7b-43b6-9bd2-22f561c30d9d)


![image](https://github.com/pochireddyp/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150232043/1d1d7b09-11d2-4df3-a7fe-837289701816)

![image](https://github.com/pochireddyp/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150232043/7b46387e-fdc1-4394-9d9f-607aea11f5ec)

![image](https://github.com/pochireddyp/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150232043/9487b3c4-55d3-4635-8d7f-82b788f7f089)

![image](https://github.com/pochireddyp/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150232043/c9b8616a-3f81-4169-8012-093befd8af2e)








## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
