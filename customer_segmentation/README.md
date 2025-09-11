# Customer segmentation (K-Means)
This project groups customers into meaningful segments using K-Means so that businesses can tailor marketing and offers.
## Dataset
Mall Customers dataset (features include Age, Annual Income, Spending Score).
## Method
- Data prep and feature scaling
- Elbow method to choose k
- Silhouette score to validate cluster quality
- K-Means clustering and 2D visualization
- Irrelevant columns (CustomerID) and categorical variables (Genre) were excluded. The clustering was performed on Age, Annual Income, and Spending Score.
## Insights from EDA
- **Spending vs. Age:** Younger customers tend to have higher spending scores than older customers.
- **Income vs. Age:** Older customers earn slightly less than younger ones.
- **Spending vs. Income:** How much a customer earns does not strongly determine how much they spend.
## Outputs
- Cluster labels and scatter plot showing segments (e.g. Budget Buyers, Mid-Spenders, Luxury Shoppers)
