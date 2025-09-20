##  CFPB Complaint Analysis - SQL & Tableau

This project analyzes over 10.9M consumer complaints from the Consumer Finanacial Protection Bureau (CFPB) database as of September 15,2025.  
I used SQL to uncover industry-wide complaint trends and benchmark company resposnse performance. I built an interactive Tableau dashboard to visualize these insights.
---

### Dataset
- **Source:** [CFPB Consumer Complaints](https://www.consumerfinance.gov/data-research/consumer-complaints/)
- **Key Fieids:** Product, Issue, Company, Date Received, Timely Response, Company response to consumer,
Complaints disputed?
---

### Steps
1.  Queried complaint counts by product and company using 'FROM' and 'GROUP BY' functions.
2.  Aggregated complaints by year (2011 - 2025) using data functions to observe complaint growth over time.
3.  Created metrics such *Timely Response Rate*, *Dispute Rate*, and *Monetary Relief Percentage* using CASE statements.
4.  Built a Tableau dashboard showcasing trends over time, top 10 companies and products with highest compalint volumes, and important KPIs (Key Performance Indicators) such as growth, timely response rates, dispute rates, and monetary relief.
 ---

### Key Insights
- **Credit reporting** accounted for over 75% of total complaints, far exceeding other categories.
- Complaint volume has increased **exponentially** over time.
- Most firms respond *timely* to complaints (> 87 %), but only about **38%** of consumer complaints receive monetary relief.
- Dispute is rare (1.35%), suggesting most consumers are satistied or do not challenge the resolution.
---

### Tableau Visualization
Explore the interactive dashboard showing complaint trends, company/product breakdowns and performance metrics.
[View on Tableau Public](https://public.tableau.com/app/profile/priyankaa.nigam/viz/CFPBComplaintsDashboard_17583408190900/CFPBDashboard)


 ### Tools
- SQLite3
- DB Browser for SQLite
- Tableau (for interactive visualizations)
