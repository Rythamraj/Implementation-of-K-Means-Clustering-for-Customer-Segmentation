# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Choose the number of clusters (K).

2.Randomly initialize K centroids.

3.Assign each data point to the nearest centroid.

4.Recalculate the centroids.

5.Repeat steps 3 and 4 until centroids do not change

## Program:
```
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans


data = pd.read_csv("Mail_Customers.csv")

print(data.head())

X = data[['Annual Income (k$)', 'Spending Score (1-100)']]

kmeans = KMeans(n_clusters=5, random_state=42)

y_kmeans = kmeans.fit_predict(X)


data['Cluster'] = y_kmeans

print("\nClustered Data:")
print(data.head())

plt.figure()
plt.scatter(X[y_kmeans == 0]['Annual Income (k$)'], 
            X[y_kmeans == 0]['Spending Score (1-100)'], label='Cluster 0')

plt.scatter(X[y_kmeans == 1]['Annual Income (k$)'], 
            X[y_kmeans == 1]['Spending Score (1-100)'], label='Cluster 1')

plt.scatter(X[y_kmeans == 2]['Annual Income (k$)'], 
            X[y_kmeans == 2]['Spending Score (1-100)'], label='Cluster 2')

plt.scatter(X[y_kmeans == 3]['Annual Income (k$)'], 
            X[y_kmeans == 3]['Spending Score (1-100)'], label='Cluster 3')

plt.scatter(X[y_kmeans == 4]['Annual Income (k$)'], 
            X[y_kmeans == 4]['Spending Score (1-100)'], label='Cluster 4')

# Plot centroids
plt.scatter(kmeans.cluster_centers_[:,0], 
            kmeans.cluster_centers_[:,1], 
            s=200, label='Centroids')

plt.title("Customer Segmentation using K-Means")
plt.xlabel("Annual Income (k$)")
plt.ylabel("Spending Score (1-100)")
plt.legend()
plt.show()

i/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Rytham Raj K R
RegisterNumber: 212225040350
*/
```

## Output:

<img width="816" height="140" alt="image" src="https://github.com/user-attachments/assets/b191f235-4d74-4a84-9eeb-5198dd83e048" />

<img width="879" height="337" alt="image" src="https://github.com/user-attachments/assets/4c157eb2-d949-47ab-bf95-fef16896181b" />

<img width="838" height="570" alt="image" src="https://github.com/user-attachments/assets/4132d6b7-525a-45d2-a638-9621fd329552" />



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
