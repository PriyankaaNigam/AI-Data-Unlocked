# U.S. Airline Market Analysis Dashboard (Tableau)

This project analyzes U.S. airline market to compare passenger traffic, pricing trends, market share, and passenger yield (cents per RPK). Using historical data (1993-2023), I built an interactive Tableau dashboard to evaluate airline competitiveness.
---

### Data Source:   
https://www.kaggle.com/datasets/amitzala/us-airline-flight-routes-and-fares

### Steps:

1.  **Data Preparation**:
    * Verified data types and removed irrelevant fields.
    * Handled missing passenger count and fare records. 
    * Mapped carrier codes to full airline names

2.  **Calculated Fields**:
   
      Key Tableau calcualtions Used: 
     * Passenger Revenue = [Passengers]*[Fare]
     * Revenue Passenger Kilometers (RPK) = [Passengers]*[Distance (miles)] * 1.60934
     * Passenger Yield (cents/RPK) =  [Passenger Revenue]/[Revenue Passenger Kilometers (RPK)])*100
     * Moving Average (Fare, 5 Year) = WINDOW_AVG(AVG(Fare]), (-2, 2)  
         
3.  **Dashboard Components**:
    
      * **Passenger Traffic trends**: Airline growth trajectory over time.
      * **Average Fare Trends**: Smoothed 5-year moving averagesto reduce voltility
      * **Market Share (2023)**: Breakdown of passenger percentage share among major carriers
      * **Passenger yield**: Cents per RPK as a measure of pricing effiiciency over time
           
### Results
 [View the Dashboard on Tableau Public](https://public.tableau.com/app/profile/priyankaa.nigam/viz/USAirlines_17613434843190/Dashboard1)


![U.S. Airline Performance Dashboard](U.S.%20Airlines%20Performance%20Dashboard.png)


### Key Insights

1. **Passenger Growth** - Sowthwest Airlines (WN) and American Airlines (AA) show the largest gains in the number of passengers.
2. **Fare Trends** - Alaska Airlines (AS) maintained the lowest fares over 20 years, while American Airlines (AA), Delta Air (DL) and United Airlines (UA) consistently charged higher fares.
3. **Market Share** - Southwest Airlines (WN) had the largest market share (28%), while Alaska Airlines (AS) held the smallest share (6%). 
4. **Passenger Yield** - Delta Air (DL) and United Airlines (UA) generally acheived higher yields (cents per RPK), while Alaska Airlines (AS) and Southwest Airlines (WN) operated at lower efficiency levels.
5. **Dot-Com Crash (2000-2002)** - Demand for higher-price Airlines (AA, DL, UA) dipped after the Dot-Com Crash while that for lower-fare arlines (AS, WN) surged.
6. **2008 Financial Crisis** - In 2009, following the financial crisis, higher-fare airlines like AA, DLand UA, sjhowed a sharper declie in passenger trafic, while low-cost SW was less impacted .
7. **COVID-19 Pandemic (2020)** - There was a sharp decrease in passenger traffic and operational efficiency during the COVVID-19 pandamic. However, both rebounded to pre-pandemic values by 2022.

### Tools

* **Tableau Desktop**
* **Excel/CSV**
