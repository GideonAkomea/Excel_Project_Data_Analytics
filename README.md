# Excel Traffic Analysis Dashboard
<img width="1544" height="1059" alt="Screenshot 2025-10-09 095731" src="https://github.com/user-attachments/assets/2ad98ed3-dd2a-4bda-9e13-d6c9e8564da9" />  

##  Introduction  
As a Civil Engineer with huge interest in Transportation Engineering and data analysis, This my first excel analysis project was carried out to gain insight into an open source traffic data obtained from kaggle.  

### Questions to Analyze  

To understand the traffic situation, i asked the following questions  

1. What is the Average Daily Traffic(ADT) per month?
2. What is the Average Annual Dialy Traffic (AADT)?
3. What is the Peak Day of the week?
4. What is the Peak Hour of the day?

### Dashboard File  
My final dashboard is in [Traffic Data Analysis](Traffic%20Analysis%20Dashboard)  

### Excel Skills Used  
The following Excel Skills were utilized for analysis  
- Charts
- Pivot Tables
- Pivot Charts
- Power Query
- DAX(Data Analysis Expressions)


### Traffic Dataset  
The dataset used for this project contains real-world traffic information from 2015 to 2017 on Kaggle available via [traffic](https://www.kaggle.com/datasets/fedesoriano/traffic-prediction-dataset/data) which provides foundation for analyzing data using Excel.It includes detailed information on:  
- ID
- Junction
- Vehicles
- DateTime

## Dashboard Build  

## Power Query (ETL)  
**Extract**  
- I first used Power Query to extract the original data [traffic data](Traffic%20Analysis%20Dashboard) and creat a query called traffic.

**Transform**  
- Then i transformed the query by reodering conlums, inserting new columns for month name, Day name, Time, Year, and date.
   - traffic  
     <img width="260" height="321" alt="Screenshot 2025-10-09 232832" src="https://github.com/user-attachments/assets/bd739fca-c75f-488c-88b2-f1fdbc229410" />

**Load**  
- Finally, i loaded the transformed query into the workbook as pivottable, setting the foundation for my subsequent analysis.
  
  <img width="1920" height="1080" alt="Screenshot (125)" src="https://github.com/user-attachments/assets/7e656ed8-03ab-4d69-a883-e5540c1b52db" />


### DAX(Data Analysis Expression)
In order to answer the question i set out initially i used dax to creat explicit measures to analyze the data based on each question.For instance:  

1. What is the Average Daily Traffic(ADT) per month?
    - i created a DAX measure ADT to answer this question.
       ```
       ADT=
       VAR TotalVehicles =
          SUM(Traffic[Vehicles])
       VAR DaysInPeriod =
          CALCULATE(
              DISTINCTCOUNT(Traffic[Date]),
              ALLEXCEPT(Traffic, Traffic[Year], traffic[Month_Recorded], Traffic[Junction])
          )
       RETURN
          DIVIDE(TotalVehicles, DaysInPeriod)
       ```



### Charts  

**Average Daily Traffic-Bar Chart**  
<img width="513" height="360" alt="Screenshot 2025-10-09 100425" src="https://github.com/user-attachments/assets/80be9576-0233-4a66-b0db-01dbc3eab2cb" />  
- **Excel Features**: Utilized bar chart feature and optimized layout for clarity.
- **Design Choice**: Horizontal bar chart for visual comparison of ADT.
- **Data Organization**: Sorted Months by decending ADT values for improved readability.
- **Insights Gained**: This enables quick identification of ADT trends in a year, noting the peak month of the displayed year and Junction was November.

**Day of the Week Traffic chart**  
<img width="455" height="340" alt="Screenshot 2025-10-09 095845" src="https://github.com/user-attachments/assets/5b27ea06-6057-4c08-bf89-60c2985463e8" />  
- **Excel Features**: Utilized bar chart feature and optimized layout for clarity.
- **Design Choice**: Vertical bar chart for visual comparison of daily traffic during the week.
- **Data Representation**: Ploted the average day of the week traffic for each day  with available data.
- **Visual Ehancement**: Did conditional formating for the peak day to be highlighted improving readability and immediate understanding of weekly traffic trend
- **Insights Gained**: Enables quick grasp of traffic trends during the week and highlights the peak day of the week.

**Time of the day Traffic Variation Chart**  
<img width="687" height="345" alt="Screenshot 2025-10-09 100439" src="https://github.com/user-attachments/assets/b2304472-05c9-4e98-945b-0cffc2f1c848" />  
- **Excel Features**: Utilized Line chart feature and optimized layout for clarity.
- **Design Choice**: Line chart to visualize time variation series.
- **Data Representation**: Ploted the average hour of the day traffic for each hour  with available data.
- **Insights Gained**: Enables quick grasp of traffic trends during the day.










