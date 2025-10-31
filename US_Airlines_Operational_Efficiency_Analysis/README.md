# U.S. Airlines Operational Efficiency Analysis Dashboard (Tableau)

This project analyzes U.S. airline operational performance to assess flight dealys, cancellations, and schedule efficiency from 1987-2020. Using historical flight data from U.S. Bureau of Transportation Sattistics (Kaggle), I built an interactive Power BI dashboard to uncover delay causes and operational trends across major airlines.
---

### Data Source:   
https://www.kaggle.com/datasets/mexwell/carrier-on-time-performance-dataset

### Steps:

1.  **Data Preparation**:
    * Loaded 2M rowsof flight data into Power BI
    * Verified data types and removed irrelevant columns (e.g., tail number, diverted airport IDS).
    * Handled missing values by letting them remain as null. 

2.  **Calculated Measures (DAX)**:
   
     * % Flight Delayed > 15 min = DIVIDE(CALCULATE(COUNTROWS(FILTER('airline_2m','airline_2m'[DepDelayMinutes]>15))),COUNTROWS('airline_2m'))*100
     * % On-Time Performance = 100 - [% Flight Delayed > 15 min]
     * Cancellation Rate =  DIVIDE(CALCULATE(COUNTROWS(FILTER('airline_2m','airline_2m'[Cancelled]=1))),COUNTROWS('airline_2m'))*100
     * Diversion Rate = DIVIDE(CALCULATE(COUNTROWS(FILTER('airline_2m','airline_2m'[Diverted]=1))),COUNTROWS('airline_2m'))*100
     * Shecule Adherance % = DIVIDE(AVERAGE('airline_2m'[CRSElapsedTime]), AVERAGE('airline_2m'[ActualElapsedTime]))*100
         
3.  **Dashboard Design**:
    
**Page 1: Overview**

**KPI cards**: On-Time %, Avg Delay, Cancellation Rate, and Diversion Rate

**Bar chart**: Average Departure Delay by Airline

**Donut chart**: On-Time vs Delayed Flights

**Slicers**: Year, Airline, and Origin City

**Page 2: Delay Analysis**

**Stacked Column**: Delay Minutes by Cause (Weather, Carrier, NAS, Security, Late Aircraft)

**Line chart**: Average Departure Delay Trend (1987–2020)

**Matrix table**: Average Delay by City

**Page 3: Operational Efficiency**

**KPI**: Schedule Adherence %

**Bar chart**: Average Taxi-Out Time by Airline

**Scatter plot**: Average AirTime vs Distance (by Airline)

**Combo Column and Line chart**: Actual vs Scheduled Flight Time Over Years
           
### Results
 [View the Dashboard on PowerBI](https://app.powerbi.com/view?r=eyJrIjoiOTQxZGZjMWItZGI3YS00YTNlLWEzOGYtOTE4M2FjZjQ1ZmVkIiwidCI6IjY2OTA5YjAzLWIxZDctNDNmYS05YmUyLTMzMmVmYzQ1YWUxMCIsImMiOjZ9)


![U.S. Airline Performance Dashboard](U.S.%20Airlines%20Performance%20Dashboard.png)


### Key Insights

1. **Passenger Growth** - Sowthwest Airlines (WN) and American Airlines (AA) show the largest gains in the number of passengers.
2. **Fare Trends** - Alaska Airlines (AS) maintained the lowest fares over 20 years, while American Airlines (AA), Delta Air (DL) and United Airlines (UA) consistently charged higher fares.
3. **Market Share** - Southwest Airlines (WN) had the largest market share (28%), while Alaska Airlines (AS) held the smalest share (6%). 
4. **Efficiency (Yield)** -Delta Air (DL) and United Airlines (UA) generally acheived higher yields (cents per RPK), while Alaska Airlines (AS) and Sowest Airlines (WN) operated at lowerefficiency levels.
5. **Dot-Com Crash (2000-2002)** - Demand for higher-price Airlines (AA, DL, UA) dipped after the Dot-Com Crash while that for lower-fare arlines (AS, WN) surged.
6. **2008 Financial Crisis** - In 2009, following the financial crisis, higher-fare airlines like AA, DLand UA, sjhowed a sharper declie in passenger trafic, while low-cost SW was less impacted .
7. **COVID-19 Pandemic (2020)** - There was a sharp decrease in passenger traffic and operational efficiency during the COVVID-19 pandamic. However, both rebounded to pre-pandemic values by 2022.

### Tools

* **Power BI**
* **Power Querry**
* **Excel/CSV**
