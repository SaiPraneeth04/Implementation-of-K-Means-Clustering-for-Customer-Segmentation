# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import all necessary packages.
2. Upload the appropiate dataset to perform K-Means Clustering.
3. Perform K-Means Clustering on the requried dataset.
4. Plot graph and display the clusters.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Sai Praneeth K
RegisterNumber:  212222230067
*/
```

```python
import pandas as pd
import numpy as np
from sklearn.cluster import KMeans
from sklearn.metrics.pairwise import euclidean_distances
import matplotlib.pyplot as plt

data=pd.read_csv('/content/Mall_Customers_EX8.csv')
data

X=data[['Annual Income (k$)','Spending Score (1-100)']]
X

plt.figure(figsize=(4,4))
plt.scatter(data['Annual Income (k$)'],data['Spending Score (1-100)'])
plt.xlabel('Annual Income (k$)')
plt.ylabel('Spending Score(1-100)')
plt.show()

k=5
kmeans=KMeans(n_clusters=k)
kmeans.fit(X)

centroids=kmeans.cluster_centers_
labels=kmeans.labels_
print("Centroids:")
print(centroids)
print("Labels:")
print(labels)

colors=['r','g','b','c','m']
for i in range(k):
  cluster_points=X[labels==i]
  plt.scatter(cluster_points['Annual Income (k$)'],cluster_points['Spending Score (1-100)'],color=colors[i],label=f'Cluster{i+1}')
  distances=euclidean_distances(cluster_points,[centroids[i]])
  radius=np.max(distances)
  circle=plt.Circle(centroids[i],radius,color=colors[i],fill=False)
  plt.gca().add_patch(circle)
plt.scatter(centroids[:,0],centroids[:,1],marker='*',s=200,color='k',label='Centroids')
plt.title('K-means Clustering')
plt.xlabel('Annual Income (k$)')
plt.ylabel('Spending Score (1-100)')
plt.legend()
plt.grid(True)
plt.axis('equal')
plt.show()
```

## Output:

## DATASET:

![8 1](https://github.com/SaiPraneeth04/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119390353/d57c1954-87b7-4d6d-9b33-4b93832b2d19)


## GRAPH:

![8 2](https://github.com/SaiPraneeth04/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119390353/fc83c204-5729-4168-9c2a-0a12b7349ba1)


## CENTROID VALUE:
![8 3](https://github.com/SaiPraneeth04/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119390353/ee1984fd-36bb-47c0-a5a8-657cdc01669b)


## K-MEANS CLUSTER:

![8 4](https://github.com/SaiPraneeth04/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119390353/e12d1f81-faa5-4508-882a-0a84f1444500)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
