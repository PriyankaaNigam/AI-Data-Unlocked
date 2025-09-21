# SQL Queries and Results for CFPB Consumer Complaints Dataset

This file includes the **SQL code**, **query results**, and **business insights** from key SQL queries performed on the CFPB Consumer Complaints dataset.

---

### Query 1: Count number of rows in the table

**SQL:**

SELECT COUNT (*) AS total_rows  
FROM complaints;

### Result:

**Total Rows:** 10,935,712

**Insight:**
Confirms the dataset was imported successfully, with over 10.9 milion complaints.

### Query 2: What are the biggest sources of consumer complaints?

**SQL:**

 SELECT Product, COUNT(*) AS total_complaints 
 FROM complaints  
 GROUP BY Product  
 ORDER BY complaint_count DESC  
 LIMIT 10;

### Result: Top 10 products by number of complaints

|     | Product                                                                     | total_complaints|
|:---:|-----------------------------------------------------------------------------|----------------:|
|  1  | Credit reporting or personal conumer reports                                |     6044466     |
|  2  | Credit reporting,credit repair services, or other personal consumer reports |     2163851     |
|  3  | Debt collection                                                             |      867403     |
|  4  | Mortgage                                                                    |      427831     |
|  5  | Checking or savings account                                                 |      308154     |
|  6  | Credit card                                                                 |      248556     |
|  7  | Credit card or prepaid card                                                 |      206368     |
|  8  | Money transfer, virtual currency, or money service                          |      152391     |
|  9  | Credit reporting                                                            |      140429     |
|  10 | Student loan                                                                |      113615     |

**Insight:**

- **Credit Reporting** is the most common source of consumer complaints, constituting more than 75% of total complaints.
- Inaccurate or disputed reports are major pain points for consumers.
- Suggests need for better credit data accuracy.
  
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
|  15 | 2025              |   3710012        |

**Insight:** 

- Clear **exponential growth** in complaints
 - From **2,536** in 2011 to over **3.6 milion** in 2025
- **Possible factors**
  - Increasing consumer awareness of CFPB 
  - Easier Online submissions
  - COVID-19 pandemic impacts on finances
  - Growing dissatisfaction with credit reporting and debt collection 

### Query 4: Which companies receive the most complaints, and how timely are their responses?

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
|  1  | Equifax, Inc                          |    2745787       |      99.94               |
|  2  | TranUnion Intermediate Hodlinngs, Inc |    2689498       |      99.99               |
|  3  | Experian Informatio Soutions, Inc     |    2495404       |      99.99               |
|  4  | Bank of America, N.A.                 |     162396       |      97.37               |
|  5  | Wells Fargo & Company                 |     151359       |      97.48               |
|  6  | JPMorgan Chase & Co.                  |     148523       |      99.94               |
|  7  | Capital One Financial Corporation     |     137388       |      99.94               |
|  8  | Citibank N.A.                         |     117464       |      99.69               |
|  9  | Synchrony Financial                   |      66762       |      99.96               |
|  10 | Block, Inc.                           |      55060       |      98.61               |

**Insight:** 

- The three major credit bureaus (Equifax, TransUnion, and Experian) have the highest number of complaints.
- Most firms have high timely response rates (> 97%).
- Large national banks like Bank of America and Wells Fargo show slightly lower response rates, possibly due to higher volume of customers.
- Indicates need for proactive customer service, not just reactive complaint handling.

### Query 5: By how much percentage has the volume of complaints grown from 2011 to 2025 YTD?

**SQL:**
SELECT 
(
(SUM(CASE WHEN strftime('%Y', "Date received") = '2025' THEN 1 ELSE 0 END) -  
SUM(CASE WHEN strftime('%Y', "Date received") = '2011' THEN 1 ELSE 0 END))  
*100)  
/SUM(CASE WHEN strftime('%Y', "Date received") = '2011' THEN 1 ELSE 0 END) AS growth_pct  
FROM complaints;


### Result:

**Growth percentage:** 146193%

**Insight:** 

- The volume of complaints has exploded between 2011 and 2025.

### Query 6: Were consumers satisfied with how the companies resolved their complaints?

**SQL:**

SELECT  
SUM(CASE WHEN LOWER(TRIM("Consumer disputed?")) = 'yes' THEN 1
 ELSE 0 
 END)  
AS disputed_count  
FROM complaints;

### Result:
**Resolutions disputed:** 148378

**SQL:**

SELECT  
SUM(CASE WHEN LOWER(TRIM("Consumer disputed?")) = 'yes' THEN 1
 ELSE 0   
 END) *100/COUNT(*)  
AS disputed_pct  
FROM complaints;

### Result:
**Percentage disputed:** 1.35%

**Insight:** 

- Most consumers are satified with the resolution of their complaints.
- Or they do not challenge the resolution.

### Query 7: What percentage of consumer complaints received monetary relief?

**SQL:**

SELECT   
SUM(CASE  
WHEN LOWER(TRIM(consumer_response)) = 'closed with monetary relief' THEN 1  
ELSE 0
END) *100  
/SUM(CASE 
WHEN LOWER(TRIM(consumer_response) <> 'in proress'THEN 1
ELSE 0
END)  
AS monetary_releif_pct  
FROM  
SELECT "Company response to consumer" AS consumer_response  
FROM complaints  
temp;

Note: Created alias for the column "Company response to consumer" as consumer_response, since SQL considers the word "to" as a keyword and it can complicate queries.

### Result:
**Percentage monetary relief:** 38%

**Insight**
- Most consumer issues are resolved without financial compensation.

