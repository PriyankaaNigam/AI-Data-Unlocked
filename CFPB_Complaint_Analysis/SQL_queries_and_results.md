# SQL Querries and Results for CFPB Consumer Complaints Dataset
---
## Query 1. 
## Count number of rows in table Complaint
SELECT 

COUNT (*) AS total_rows

FROM complaints

### Result/Insight: 
### 10,935,662

This matches data size, conforming that data was imported successfully.

## Query 2. 
## What are the biggest sources of consumer complaints?

 SELECT Product,
 
 COUNT(*) AS complaint_count

 FROM complaints
 
 GROUP BY Product

 ORDER BY complaint_count DESC
 
 LIMIT 10;

### Result/Insight:

### Top 10 products by number of complaints

| Rank | Product                                                                    | Complaint Count |
|:---:|-----------------------------------------------------------------------------|----------------:|
|  1  | Credit reporting or personal conumer reports                                |     6026988     |
|  2  | Credit reporting,credit repair services, or other personal consumer reports |     2163851     |
|  3  | Debt collection                                                             |      866980     |
|  4  | Mortgage                                                                    |      427829     |
|  5  | Checking or savings account                                                 |      308148     |
|  6  | Credit card                                                                 |      248461     |
|  7  | Credit card or prepaid card                                                 |      206368     |
|  8  | Money transfer, virtual currency, or money service                          |      152380     |
|  9  | Credit reporting                                                            |      140429     |
|  10 | Student loan                                                                |      113611     |
