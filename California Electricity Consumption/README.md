# California Electricity Consumption Dashboard (1990-2024)

This project analyzes 35 years of California electricity consumption data to identify usage trends across sectors, agencies, and utlity types. 
The goal is to explore how different sectors (Commercial, Residential, Industrial, etc.) contribute to total electricity demand and Carbon dioxide emission and how consumption patterns have evloved over time using an interactive Power BI dashboard. The tool supports clean-energy program planning by identifying high-impact sectors for energy efficiency (EE), demand response (DR), and electrification initiatives.
---

### Data Source:   
https://www.energy.ca.gov/files/energy-consumption-data-files

### Steps:
1.  **Data Cleaning & Transformation (Power Query)**:
    * Promoted headers and verified data types.
    * Converted column names to consistent casing for readability.
    * Used Power Query's "Remove Empty" to filter out blanks in Electric Cosumption column.
    * Ensured columns were formatted corretly as texts and decimals.

2. **DAX Measure**:
       CO₂e (Mt) = Total Electricity (GWh) × 0.195/1000

   GHG = greenhouse gases. CO₂e denotes total GHG expressed as CO₂-equivalent (100-yr GWP). This dashboard uses eGRID 2023 CAMX average 0.195 tCO₂e/MWh to convert GWh to CO₂e.

3.  **Dashboard Components**:
   
      Developed a clean, interactive dashboard with filters and dynamic visuals. 
      
      * **KPI Card**: Total Electricity (GWh), Estimated CO₂e emission (Mt)
      * **Interactive Slicers**: Year, Agency Name, Agency Type, Sector
      * **Visualizations**: 
        1. **Bar Chart**: Total Electricity Consumption (GWh) by Agency
        2. **Column Chart**: Total Electricity Consumption (GWh) by Sector
        3. **Column Chart**: Total Carbon emission (Mt) by Sector
        4. **Line Chart**: Yearly electricity Consumption and Carbon Emission Trend 

 4.  **Publishing**:
    
      Published dashboard to Power BI Service for interactive exploration.

### Results
 [View the Interactive Dashboard Live](https://app.powerbi.com/view?r=eyJrIjoiMTYxYTQzNTMtMzg0Mi00MTdiLWI4ZTItMmMwYTVlNjE1ZjUxIiwidCI6IjY2OTA5YjAzLWIxZDctNDNmYS05YmUyLTMzMmVmYzQ1YWUxMCIsImMiOjZ9)

### Key Insights:
**Scale & Carbon Footprint**: 

 Over 35 years, California's electricity sector generated 9.25M GWh electricity. This translates to an estimated 1,800 megatons (1.8 gigatons) of cumulative CO₂e emissions, which is equivalent to the annual emissions of ~390 million cars. Annual emissions peaked around 2007 at ~56 Mt/year and have plateaued at ~55 Mt/year through 2024.
 SCE serves ~79.3K GWh (≈28% of CA), making it a co-leader with PG&E. Therefore, even small percentage improvements at SCE produce outsized statewide carbon and reliability benefits. Every 1% efficiency gain at SCE avoids approximately 55 Mt of cumulative emission over 10 years.

**Sector Breakdown & Emissions Impact**: 

Commercial + Residential = ~68% of Statewide electricity consumption load AND ~68% of emissions (1,220 Mt cumulative). So these sectors are prime targets for EE(Energy Efficiency) retrofits, DR (Demand Response) programs, and building electrification.
Rising Transportation share: For SCE, trnsportation load rose from 4.3K to 6.4K GWh, consistent with rise in Electic Vehicle adoption signals EV adoption. There is an opportunity for managed charging to absorb midday solar and keep incremental load low-carbon

**Overall Trend**:

Loads rose into ~2010, then plateaued, with a 2020 dip and partial recovery. This is consistent with codes & standards, EE, and behind-the-meter (BTM) solar dampening growth. 

### Tools:
Power BI (PowerQuery, DAX)
