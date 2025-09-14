# SQL Queries and Results for CFPB Consumer Complaints Dataset

This fie includes the **SQL code**, **query results**, and **business insights** from key SQL queries performed on the CFPB Consumer Complaints dataset.

---

### Query 1: Count number of rows in the table

**SQL:**

SELECT COUNT (*) AS total_rows  
FROM complaints;

### Result:

**Total Rows:** 10,935,662

**Insight:**
Confirms the dataset was imported successfully, with over 10.9 milion complaints.

### Query 2: What are the biggest sources of consumer complaints?

**SQL:**

 SELECT Product, COUNT(*) AS complaint_count  
 FROM complaints  
 GROUP BY Product  
 ORDER BY complaint_count DESC  
 LIMIT 10;

### Result: Top 10 products by number of complaints

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

**Insight:**

- **Credit Reporting** is the most common source of consumer complaints, constituting more than 55% of total complaints.
- Inaccurate or disputed reported are major pain points for consumers.
- Suggests need for better credit data accuracy and dispute resolution.
  
### Query 3: How have complaint volumes changed over time?

**SQL:**

SELECT STRFTIME('%Y', "Date received") AS complaint_year,   
COUNT(*) AS total_complaints         
FROM complaints  
GROUP BY complaint_year  
ORDER BY complaint_year;

### Result: Total Complaints over Time (2011-2025)

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

**Insight:** 

- Clear **exponential growth** in complaints
 - From **2,536** in 2011 to over **3.6 milion** in 2025
- **Possible factors**
  - Increasing consumer awareness of CFPB 
  - Easier Online submissions
  - COVID-19 pandemic impacts on finances
  - Growing dissatisfaction with credit reporting and debt collection 

## Query 4 
## Which companies receive the most complaints, and how timely are their responses?

**SQL:**
 SELECT Company,
 COUNT(*) AS total_complaints,  
 SUM(CASE WHEN "Timely response?" = 'Yes' THEN 1 ELSE 0 END) * 100.0 / COUNT(*) AS timely_response_rate_pct 
 FROM complaints  
 GROUP BY Company  
 ORDER BY total_complaints DESC  
 LIMIT 10;

### Result: Top 10 companies by complaints and their response rates

|     | Company                               | total_complaints | timely_response_rate_pct |
|:---:|---------------------------------------|------------------|-------------------------:|
|  1  | Equifax, Inc                          |    2738795       |      99.94               |
|  2  | TranUnion Intermediate Hodlinngs, Inc |    2681896       |      99.99               |
|  3  | Experian Informatio Soutions, Inc     |    2492174       |      99.99               |
|  4  | Bank of America, N.A.                 |     162396       |      97.37               |
|  5  | Wells Fargo & Company                 |     151359       |      97.48               |
|  6  | JPMorgan Chase & Co.                  |     148523       |      99.94               |
|  7  | Capital One Financial Corporation     |     117454       |      99.94               |
|  8  | Citibank N.A.                         |      66762       |      99.69               |
|  9  | Synchrony Financial                   |      55060       |      99.96               |
|  10 | Block, Inc.                           |      117454      |      98.61               |

**Insight:** 

- The three major credit bureaus (Equifax, TransUnion, and Experian) have the highest number of complaints.
- Most firms have high timely response rates (> 97%).
- Large national banks like Bank of America and Wells Fargo show slightly lower response rates, possibly due to higher volume of customers.
- Indicates need for proactive customer service, not just reactive complaint handling.
