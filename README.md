# K-Means Clustering on Mall Customers

This project implements K-Means clustering to segment customers based on their **Annual Income** and **Spending Score** using the `Mall_Customers.csv` dataset. This project can be easily adapted to work with other datasets containing different or additional independent variables.

## Project Overview

Customer segmentation is a popular use case in marketing and retail analytics. By applying the K-Means clustering algorithm, this project identifies distinct groups of customers to help businesses target specific customer segments more effectively.

## Key Features

- Uses the Elbow Method to determine the optimal number of clusters.
- Applies K-Means clustering to segment the customers.
- Visualizes the resulting clusters and centroids using matplotlib.

## Getting Started

### Prerequisites

Before running the code, make sure the following Python libraries are installed:

```bash
pip install numpy pandas matplotlib scikit-learn
```

### Steps to Run the Project

1. **Download the dataset:** Ensure `Mall_Customers.csv` is in the same directory as your script.
2. **Run the Python script:** Execute the provided `.py` file to perform clustering and view the results.
3. **Elbow Method Visualization:** A line graph showing WCSS (Within-Cluster Sum of Squares) helps determine the optimal number of clusters.
4. **Cluster Visualization:** A scatter plot visualizes the customer clusters and their respective centroids.

## Output

- **Elbow Method Graph** to select the optimal number of clusters.
  
  ![Image](https://github.com/user-attachments/assets/51fc8343-1af1-4e42-97e5-3ac65dd6e373)
- **Cluster Plot** highlighting different customer segments.
  
  ![Image](https://github.com/user-attachments/assets/9a1551fd-c836-44a0-a3be-56f83465b9cd)

## License

This project is open-source and available under the MIT License.
