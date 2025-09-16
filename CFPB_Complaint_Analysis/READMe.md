#  CPFB Complaint Analysis - SQL 

###This project analyzes over 10M+ consumer complainsts from the Consumer Finanacial Protection Bureau (CFPB) database.  

I used SQL to identify industry-wide complaint trends and created new metrics to benchmark customer service performance.

## Dataset
- **Source:** [CFPB Consumer Complaints](https://www.consumerfinance.gov/data-research/consumer-complaints/)
- **Feature:** Product, Issue, Company, Date Received, Timely Response

## Steps
1. **EDA:** Queried complaint counts by product and company.
2. **Trend Analysis:** Aggregated complaints by year using data functions to observe growth over time.
3. **New Metric:** Created a "timely Response Rate" metric using CASE statements to evaluate company service quality.

## Key Insights
- **Credit reporting** accounted for over 55% of total comlaints, far exceeding other categories.
- Complaint volume has increased **exponentially** over time.
- Although many firms have very high complaint counts, they give a timely repsonse to complaints (>97%)
- Suggests necessity for proactive customer service rather than reactive complaint management.

##Tools
- SQLite3
- DB Browser for SQLite
