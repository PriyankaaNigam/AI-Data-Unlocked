# SQL Analysis of the CPFB Consumer Complaint Database

## This project analyzes over 10M+ consumer complainsts from the Consumer Finanacial Protection Bureau (CFPB) database.  
I used SQL to identify industry-wide complait trends and created new metrics to benchmark customer service performance.


## Dataset
- **Source:** [CFPB Consumer Complaints](https://www.consumerfinance.gov/data-research/consumer-complaints/)
- **Feature:** Product, Issue, Company, Date Received, Timely Response

## Steps
1. **EDA:** Queried complaint counts by product and company.
2. **Trend Analysis:** Aggregated complaints by year using data functions to observe growth over time.
3. **New Metric:** Created a "timely Response Rate" metric using CASE statements to evaluate company service quality.

## Key Insights
- Credit reporting is the top complaint (>55% of complaints)
- Complaint volume has increased exponentially over time
- Many firms respond on time despite hiher complaint counts

##Tools
- SQLite3
- DB Drowser for SQLite
