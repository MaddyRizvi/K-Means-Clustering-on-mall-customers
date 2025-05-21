# K-Means Clustering on Mall Customers Dataset

This project demonstrates how to use the K-Means clustering algorithm to segment customers based on their annual income and spending score using the `Mall_Customers.csv` dataset.

## Dataset

The dataset used in this project is `Mall_Customers.csv`, which contains the following features:

- CustomerID
- Gender
- Age
- Annual Income (k$)
- Spending Score (1-100)

## Getting Started

### Prerequisites

Ensure you have the following Python libraries installed:

```bash
pip install numpy pandas matplotlib scikit-learn
```

### Running the Code

1. Load the dataset using pandas.
2. Apply K-Means clustering using the elbow method to determine the optimal number of clusters.
3. Visualize the clusters and centroids.

```python
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
from sklearn.cluster import KMeans

# Load data
dataset = pd.read_csv('Mall_Customers.csv')
X = dataset.iloc[:, [3, 4]].values

# Elbow method
wcss = []
for i in range(1, 11):
    kmeans = KMeans(n_clusters=i, init='k-means++', random_state=42)
    kmeans.fit(X)
    wcss.append(kmeans.inertia_)
plt.plot(range(1, 11), wcss)
plt.title('The Elbow Method')
plt.xlabel('Number of clusters')
plt.ylabel('WCSS')
plt.show()

# K-Means Clustering
kmeans = KMeans(n_clusters=5, init='k-means++', random_state=42)
y_kmeans = kmeans.fit_predict(X)

# Visualize Clusters
plt.scatter(X[y_kmeans == 0, 0], X[y_kmeans == 0, 1], s=100, c='red', label='Cluster 1')
plt.scatter(X[y_kmeans == 1, 0], X[y_kmeans == 1, 1], s=100, c='blue', label='Cluster 2')
plt.scatter(X[y_kmeans == 2, 0], X[y_kmeans == 2, 1], s=100, c='green', label='Cluster 3')
plt.scatter(X[y_kmeans == 3, 0], X[y_kmeans == 3, 1], s=100, c='cyan', label='Cluster 4')
plt.scatter(X[y_kmeans == 4, 0], X[y_kmeans == 4, 1], s=100, c='magenta', label='Cluster 5')
plt.scatter(kmeans.cluster_centers_[:, 0], kmeans.cluster_centers_[:, 1], s=300, c='yellow', label='Centroids')
plt.title('Clusters of customers')
plt.xlabel('Annual Income (k$)')
plt.ylabel('Spending Score (1-100)')
plt.legend()
plt.show()
```

## Output

- Elbow Method graph to determine optimal clusters.
- Visual representation of clusters and their centroids.

## License

This project is licensed under the MIT License.