# SQL Queries and Results for CFPB Consumer Complaints Dataset
---
## Query 1. 
## Count number of rows in table Complaint
SELECT COUNT (*) AS total_rows

FROM complaints

### Result/Insight: 
### 10,935,662

This matches data size, conforming that data was imported successfully.

## Query 2. 
## What are the biggest sources of consumer complaints?

 SELECT Product, COUNT(*) AS complaint_count

 FROM complaints
 
 GROUP BY Product

 ORDER BY complaint_count DESC
 
 LIMIT 10;

### Result/Insight:

### Top 10 products by number of complaints

|     | Product                                                                     | complaint_count |
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

The most common source of consumer complaints is credit reporting, constituting more than 55% of total complaints.

## Query 2. 
## How have complaint volumes changed over time?

SELECT STRFTIME('%Y', "Date received") AS complaint_year, 
COUNT(*) AS total_complaints
       
FROM complaints

GROUP BY complaint_year

ORDER BY complaint_year;

### Result/Insight:

### Total Complaints over Time

|     | complaint_year    | total_complaints |
|:---:|-------------------|-----------------:|
|  1  | 2011              |      2536        |
|  2  | 2012              |     72372        |
|  3  | 2013              |    108215        |
|  4  | 2014              |    153001        |
|  5  | 2015              |    168429        |
|  6  | 2016              |    191401        |
|  7  | 2017              |    242840        |
|  8  | 2018              |    257198        |
|  9  | 2019              |    277287        |
|  10 | 2020              |    444284        |
|  11 | 2021              |    495987        |
|  12 | 2022              |    800340        |
|  13 | 2023              |   1292107        |
|  14 | 2024              |   2737703        |
|  15 | 2025              |   3691962        |

Data shows a **clear exponential upward trend** in the number of consumer complaints filed with CFPB (Consumer Finance Protection Board). 

Complaints rose from just **2,536** in 2011 to over **3.6 milion** in 2025

**Possible factors**
- Increasing consumer awareness of CFPB 
- Easier Online submissions
- Economic conditions such as COVID-19 pandemic
- Increasing dissatisfaction with financial products such as credit reporting and debt collection 

