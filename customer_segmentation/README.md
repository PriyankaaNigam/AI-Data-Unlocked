# Customer segmentation with K-Means
This project groups mall customers into segments using **K-Means clustering**.
Its part of my learning journey in data science (**EDA**, **data preprocessing**, and **unsupervised machine learning**).
## Dataset
Mall_Customers dataset (https://www.kaggle.com/datasets/shwetabh123/mall-customers
(Features: Age, Annual Income, Spending Score)
---
## Steps
1. **EDA** - Explored data with histograms, boxplots, and correlations
2. **Preprocessing** - Cleaned data and scaled features with MinMaxScaler
3. **Clustering** - Used **Elbow Method** and **Solhouette Score** to find the best number of clusters (k=6) 
4. **Results**  - Visuaized clusters, added cluster centers, and compared groups 
  
## Key Insights
- Younger customers tend to spend more than older customers.
- Income does not always predict spending.
- Segments include groups like *young high spenders*, *older mid-spenders*, *high income-high spenders*, and *budget buyers*.
- Businesses can use these clusters to help design better marketing .

## Tools / Libraries
- Python (Jupyter Notebook)
- pandas, matplotlib,scikit-learn
