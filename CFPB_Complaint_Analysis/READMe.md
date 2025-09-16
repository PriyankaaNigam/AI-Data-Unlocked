#  CFPB Complaint Analysis - SQL 

### This project analyzes over 10M+ consumer complaints from the Consumer Finanacial Protection Bureau (CFPB) database.  

I used SQL to identify industry-wide complaint trends and created new metrics to benchmark customer service performance.

## Dataset
- **Source:** [CFPB Consumer Complaints](https://www.consumerfinance.gov/data-research/consumer-complaints/)
- **Key Fieids:** Product, Issue, Company, Date Received, Timely Response

## Steps
1.  Queried complaint counts by product and company using FROM and GROUP BY functions.
2.  Aggregated complaints by year using data functions to observe growth over time.
3.  Created a "Timely Response Rate" metric using CASE statements to evaluate company service quality.

## Key Insights
- **Credit reporting** accounted for over 55% of total complaints, far exceeding other categories.
- Complaint volume has increased **exponentially** over time.
- Although many firms have very high complaint counts, they give a timely respsonse to consumers (>97%)
- Suggests necessity for proactive customer service rather than reactive complaint management.

 ## Tools
- SQLite3
- DB Browser for SQLite
