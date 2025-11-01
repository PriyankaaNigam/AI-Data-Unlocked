# U.S. Airlines Operational Efficiency Analysis Dashboard (Tableau)

This project analyzes U.S. airline operational performance to assess flight dealys, cancellations, and schedule efficiency from 1987-2020. Using historical flight data from U.S. Bureau of Transportation Sattistics (Kaggle), I built an interactive Power BI dashboard to uncover delay causes and operational trends across major airlines.
---

### Data Source:   
https://www.kaggle.com/datasets/mexwell/carrier-on-time-performance-dataset

### Steps:

1.  **Data Preparation**:
    * Loaded 2M rows of flight data into Power BI
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

## Delay Cause Glossary

This glossary summarizes the five official delay categories defined by the **U.S. Bureau of Transportation Statistics (BTS)**.  
Each cause represents a distinct source of flight delay affecting overall on-time performance.

| **Delay Cause** | **Detailed Definition** | **Typical Control** | **Example** | **Key Insight** |
|------------------|--------------------------|----------------------|--------------|------------------|
| **Carrier Delay** | Delays due to circumstances **within the airline’s control**, such as maintenance, crew scheduling, fueling, or baggage handling. | **Airline** | Crew or aircraft unavailable, slow turnaround, or late connecting passengers. | Indicates **operational inefficiency**; strong signal of process or scheduling issues within the airline. |
| **Weather Delay** | Delay caused by **significant meteorological conditions** that affect safe flight operations. | **Uncontrollable (Nature)** | Thunderstorms, snowstorms, fog, or high winds causing temporary ground stops. | Reflects **environmental impact** on airline reliability; tends to spike seasonally by region. |
| **NAS Delay (National Airspace System)** | Delays originating from **air traffic control, airport congestion, or airspace restrictions**. | **FAA / Airport Authority** | Ground holds, limited takeoff slots, or heavy air traffic near large hubs. | Represents **system-level congestion** rather than airline performance; common at busy airports like ATL or ORD. |
| **Security Delay** | Delay caused by **airport security issues or procedures** disrupting scheduled operations. | **TSA / Airport** | Security breaches, evacuations, or secondary passenger screening delays. | Usually rare but **high impact**; linked to heightened alert periods or specific incidents. |
| **Late Aircraft Delay** | Delay resulting when a **plane arrives late from its previous flight**, preventing on-time turnaround for its next leg. | **Airline + Network** | An aircraft arriving 45 min late from Chicago delays its next departure to Los Angeles. | The **largest and most persistent** delay category; reflects cascading effects of prior delays across the network. |

---

*Understanding these categories helps interpret trends in the dashboard’s “Delay Minutes by Cause” visual and identify where operational improvements can yield the greatest efficiency gains.*

           
### Results
 [View the Dashboard on PowerBI](https://app.powerbi.com/view?r=eyJrIjoiOTQxZGZjMWItZGI3YS00YTNlLWEzOGYtOTE4M2FjZjQ1ZmVkIiwidCI6IjY2OTA5YjAzLWIxZDctNDNmYS05YmUyLTMzMmVmYzQ1YWUxMCIsImMiOjZ9)


![U.S. Airline Performance Dashboard](U.S.%20Airlines%20Performance%20Dashboard.png)


### Key Insights

1. **On-Time Performance** - 84.2% of flights from the eight major U.S. carriers departed within 15 minutes of scheduled time.
2. **Major Delay Causes** - Aircraft delays i.e. plane arriving late from its prior flight and Carrier delay i.e internal airline issues.
3. **Market Share** - Southwest Airlines (WN) had the largest market share (28%), while Alaska Airlines (AS) held the smalest share (6%). 
4. **Efficiency (Yield)** -Delta Air (DL) and United Airlines (UA) generally acheived higher yields (cents per RPK), while Alaska Airlines (AS) and Sowest Airlines (WN) operated at lowerefficiency levels.
5. **Dot-Com Crash (2000-2002)** - Demand for higher-price Airlines (AA, DL, UA) dipped after the Dot-Com Crash while that for lower-fare arlines (AS, WN) surged.
6. **2008 Financial Crisis** - In 2009, following the financial crisis, higher-fare airlines like AA, DLand UA, sjhowed a sharper declie in passenger trafic, while low-cost SW was less impacted .
7. **COVID-19 Pandemic (2020)** - There was a sharp decrease in passenger traffic and operational efficiency during the COVVID-19 pandamic. However, both rebounded to pre-pandemic values by 2022.

### Tools

* **Power BI**
* **Power Querry**
* **Excel/CSV**
