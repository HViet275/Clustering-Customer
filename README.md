# Customer Clustering and Recommendation System :convenience_store:

## Overview :fire:

This project is in progress and focuses on enhancing marketing strategies and increasing sales for an online retailer through customer segmentation and a recommendation system. By analyzing transactional data, we aim to segment customers into distinct clusters and recommend personalized products.

## Dataset [https://drive.google.com/drive/folders/1rXyRjaZ5946gTyQ1DijMxkD6nW9by-3D?usp=drive_link] :fire:

The dataset used includes sales transactions from a UK-based retailer and contains the following columns:

- **InvoiceNo**: Unique identifier for each transaction.
- **StockCode**: Product code for each item.
- **Description**: Product description (with some missing values).
- **Quantity**: Quantity of items purchased.
- **InvoiceDate**: Date and time of the transaction (already in datetime format).
- **UnitPrice**: Price per unit of each product.
- **CustomerID**: Unique identifier for each customer (with some missing values).
- **Country**: Country where the transaction occurred.

## Objectives :fire:

1. **Customer Clustering**:
   - **Goal**: Segment customers based on their purchasing behavior.
   - **Method**: K-means clustering algorithm.
   - **Tools**: `sklearn.cluster.KMeans`, `yellowbrick.cluster.KElbowVisualizer`, `yellowbrick.cluster.SilhouetteVisualizer`.
   - **Outcome**: Identify customer segments and analyze their characteristics to improve marketing strategies.

2. **Recommendation System**:
   - **Goal**: Suggest top-selling products to customers within each segment who have not yet purchased those items.
   - **Method**: Collaborative filtering and content-based recommendations.
   - **Outcome**: Increase sales and marketing effectiveness through tailored product suggestions.

## Current Status :fire:

We are currently coding and implementing the following tasks:

1. **Data Cleaning**:
   - Handling missing values in `Description` and `CustomerID`.
   - Addressing negative values in `Quantity` and `UnitPrice`.

2. **Feature Engineering**:
   - Creating new features to better represent customer behavior and transaction patterns.

3. **Clustering**:
   - Applying K-means clustering and evaluating results using silhouette score, Calinski-Harabasz score, and Davies-Bouldin score.
   - Visualizing clustering performance using `matplotlib` and `seaborn`.
  ![Silhouette Plot](https://github.com/user-attachments/assets/2d9cacab-b2f2-4929-8876-08a781f84309)



4. **Visualization**:
   - Generating visualizations of data and clustering results using `matplotlib`, `seaborn`, and `plotly`.
   - ![3D_Clustering](https://github.com/user-attachments/assets/6d41b684-effb-43fd-a635-e27ccf081f38)


:bulb: 5. **Recommendation System**: :bulb:

In the final phase of this project, a recommendation system will be developed to enhance the online shopping experience by suggesting products based on customer segments. Here’s a step-by-step approach to how the system will be built:

**Data Preparation**:
   - Isolate a small fraction (5%) of the customers identified as outliers and store them in a separate dataset called `outliers_data`.
   - Focus on the remaining 95% of the customer group, ensuring data consistency and accuracy.

**Data Filtering and Merging**:
   - Extract the CustomerIDs of the outliers and remove their transactions from the main dataframe.
   - Ensure consistent data types for `CustomerID` across both datasets before merging.
   - Merge the filtered transaction data with customer data to incorporate cluster information.

**Top-Selling Products Identification**:
   - Identify the top 10 best-selling products in each cluster based on the total quantity sold.
   - Sort and rank products within each cluster to determine the most popular items.

**Customer Purchase Tracking**:
   - Create a record of products purchased by each customer within their respective clusters.

**Generate Recommendations**:
   - For each customer in each cluster, identify products that they have not yet purchased but are among the top 3 best-selling products in their cluster.
   - Generate a list of personalized product recommendations for each customer.

**Recommendation Output**:
   - Compile the recommendations into a dataframe that includes suggested products for each customer.
   - Merge this recommendation data with the original customer data to provide a comprehensive view of customer preferences and suggestions.

For customers in the outlier group, a basic approach will be to recommend random products as a starting point to engage them.

This recommendation system aims to deliver tailored product suggestions, enhance targeted marketing strategies, and ultimately boost sales by improving the personalized shopping experience.


## Tools and Libraries :fire:

- **Programming Language**: Python
- **Libraries**:
  - `numpy`, `pandas`
  - `seaborn`, `matplotlib`, `plotly`
  - `scipy.stats.linregress`
  - `sklearn.ensemble.IsolationForest`, `sklearn.preprocessing.StandardScaler`, `sklearn.decomposition.PCA`, `sklearn.cluster.KMeans`
  - `yellowbrick.cluster.KElbowVisualizer`, `yellowbrick.cluster.SilhouetteVisualizer`
  - `tabulate`, `collections.Counter`
- **Warnings**: Suppressed using `warnings.filterwarnings('ignore')`

## Next Steps

- Complete the implementation of the clustering and recommendation system.
- Evaluate and refine the results to enhance segmentation and recommendations.
- Conduct further analysis to refine marketing strategies based on the insights gained.
