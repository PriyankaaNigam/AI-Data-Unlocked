# Mall Customer segmentation with K-Means Clustering

This project focuses on identifying distinct customer segments based on their age, income, and spending habits with the goal of providing the mall's marketing team with actionable insights to develop targeted strategies, enhance customer engagement, and optimize marketing spend. K-means clustering, an unsupervised machine learning technique, can uncover patterns in customer data that are not immediately obvious.

## Dataset
Mall_Customers dataset (https://www.kaggle.com/datasets/shwetabh123/mall-customers
Features: Age, Annual Income, Spending Score
---
## Steps
1. **EDA** - Explored data with histograms, boxplots, and correlations
2. **Preprocessing** - Cleaned data and scaled features with MinMaxScaler
3. **Clustering** - Used **Elbow Method** and **Solhouette Score** to find the optimal number of clusters (k=5) 
4. **Results**  - Visualized clusters, added cluster centers, and compared groups 
  
## Results
The analysis segmented customers into 5 distinct personas:

| Cluster | Persona Name           | Avg. Age | Avg. Annual income ($) | Avg. Spending Score | Characteristics                                                     |
|:--------|------------------------|----------|------------------------|:-------------------:|--------------------------------------------------------------------:|
|   0     | **Prime Spenders**     |   33     |           86,000       |       82            | High income, high spending. Most valuable customers                 | 
|   2     | **Eager Shoppers**     |   26     |           26,000       |       79            | Young, low income, high spending. Limited budget but trend-conscious|
|   3     | **Cautious Buyers**    |   44     |           90,000       |       18            | High income, very low spending. Careful and selective spenders      |
| 1 & 4   | **Standard Customers** |  27-56   |           50,000       |       42            | Average income, average spending. General mall visitors             |

## Business Recommendations: Marketing strategies
1. **Prime Spenders:** Target with luxury brands, exclusive events, premium loyaly programs
2. **Eager Shoppers:** Social media campaigns, student discounts, 'buy now, pay later' financing options
3. **Cautious Buyers:** Targeted ads for high value, high quality items
4. **Standard Customers:** Mall-wide seasonal events, general promotions, standard loyalty rewards

## Tools / Libraries
- Python 
- pandas, matplotlib, scikit-learn
- Jupyter Notebook
