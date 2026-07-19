# 📊 Bike Stations Sharing Data Analysis 

A Power BI dashboard that analyzes public bike-sharing station operations to monitor bike availability, station utilization, contract performance, and geographic distribution, enabling data-driven operational decisions.

---

# 📑 Table of Contents

- Project Overview
- Data Sources & Architecture
- Data Transformation (ETL)
- Data Model & DAX
- Dashboard Features
- Key Insights
- How To Use

---

# 🎯 Project Overview
## Business Problem
Public bike-sharing operators need continuous visibility into station availability, bike utilization, and operational performance. Without centralized analytics, identifying empty stations, full stations, and underperforming contracts becomes difficult, resulting in poor customer experience and inefficient bike redistribution
## Objective
This dashboard helps stakeholders monitor bike-sharing operations by analyzing:
- Station availability
- Bike utilization
- Capacity utilization
- Contract-wise performance
- Geographic distribution of bike stations
- Operational KPIs for efficient resource planning
The ultimate goal is to improve network efficiency, optimize bike redistribution, and enhance customer satisfaction.

## Target Audience
- Operations Managers
- City Transportation Authorities
- Business Analysts
- Executive Leadership
- Smart Mobility Planning Teams
---
# 🗃️ Data Sources & Architecture
## Source System
- Open Government Data – Public Bike Sharing System Dataset
## Dataset Information
The dataset contains:
- Station Number
- Station Name
- Address
- Latitude & Longitude
- Contract Name (City)
- Operational Status
- Bike Stands
- Available Bikes
- Available Bike Stands
- Banking Facility
- Bonus Station Indicator
- Last Updated Timestamp
## Data Coverage
- Time Period: **2020–2025**
- Domain: **Smart Transportation / Urban Mobility**
## Storage Mode
- **Import Mode**
---
# ⚙️ Data Transformation (ETL)
## Tool Used
- Power Query Editor
## Data Cleaning Activities
- Removed duplicate records
- Handled missing values
- Standardized text formatting
- Trimmed unnecessary spaces
- Converted data types
- Created calculated columns
- Applied filtering and sorting
- Removed unnecessary columns
- Optimized data for reporting

## Custom Transformations
- Capacity utilization calculations
- Operational status indicators
- Data quality improvements
- Relationship optimization
---

# 🧠 Data Model & DAX

## Fact Table
- **Feuil1 (Bike Station Data)**
## Dimension Attributes
- Contract
- Status
- Banking
- Bonus
- Geographic Location
- Last Update

## Key DAX Measures
```DAX
1.	Average Available Bike Stands = AVERAGE('Feuil1'[Available Bike Stands])
2.	Average Available Bikes = AVERAGE('Feuil1'[Available Bikes])
3.	Average Capacity = AVERAGE('Feuil1'[Bike Stands])
4.	Banking Stations = COUNTROWS(FILTER('Feuil1','Feuil1'[Banking] = TRUE()))
5.	Bikes In Use = SUM('Feuil1'[Bike Stands]) - SUM('Feuil1'[Available Bikes])
6.	Bonus Stations = COUNTROWS(FILTER('Feuil1','Feuil1'[Bonus] = TRUE()))
7.	Capacity Utilization % = DIVIDE([Bikes In Use],[Total Bike Stands],0)
8.	Closed Station % = DIVIDE([Closed Stations],[Total Bike Stands])
9.	Closed Stations = COUNTROWS(FILTER('Feuil1','Feuil1'[Status] = "CLOSED"))
10.	Empty Stations = COUNTROWS(FILTER('Feuil1','Feuil1'[Available Bikes] = 0))
11.	Full Stations = COUNTROWS(FILTER('Feuil1','Feuil1'[Available Bike Stands] = 0))
12.	Open Station % = DIVIDE([Open Stations],[Total Bike Stands])
13.	Open Stations = CALCULATE(COUNTROWS('Feuil1'),'Feuil1'[Status] = "OPEN"))
14.	Open Stations 2 = COUNTROWS(FILTER('Feuil1','Feuil1'[Status] = "OPEN"))
15.	Operational Rate = DIVIDE([Open Stations],COUNTROWS(Feuil1))
16.	Total Available Bikes = SUM('Feuil1'[Available Bikes])
17.	Total Bike Stands = COUNT(Feuil1[Bike Stands])
```
Additional KPIs include:
- Average Available Bikes
- Average Capacity
- Banking Stations
- Bonus Stations
- Open Station %
- Closed Station %
---
# 🖥️ Dashboard Features
## 📄 Page 1 – Contract Analysis

- Contract-wise station count
- Bike stand distribution
- Open vs Closed stations
- KPI Cards
- Interactive slicers

---
## 📄 Page 2 – Station Performance

- Capacity utilization
- Available bikes
- Empty stations
- Full stations
- Performance comparison
- Drill-down analysis
---
## 📄 Page 3 – Geographic Analysis

- Interactive Map
- Geographic station distribution
- Contract-level comparison
- Location-based insight
---

## Interactive Features
- KPI Cards
- Bar Charts
- Line Charts
- Pie & Donut Charts
- Treemap
- Map Visualizations
- Tables & Matrix
- Drill-down
- Cross-filtering
- Dynamic Slicers

## Design Theme

- Clean professional layout
- Consistent color palette
- Interactive navigation
- Easy-to-read KPI cards
- Responsive filtering experience
---
# 💡 Key Insights

### 🚲 Trend A
Approximately **93%** of bike stations are operational, indicating a highly reliable bike-sharing network.
### 📍 Trend B

Cities including **Lyon**, **Toulouse**, and **Bruxelles-Capitale** have the highest concentration of stations and bike stands, reflecting greater transportation demand.

### ⚠️ Operational Findings
- Around **705** stations have no available bikes.
- Around **335** stations are completely full.
- Most stations do not provide banking facilities.
- Bike availability varies significantly across cities.

### 📈 Recommendation
- Prioritize bike redistribution to empty stations.
- Increase bike collection from full stations.
- Expand docking capacity in high-demand cities.
- Implement demand forecasting for proactive bike allocation.
- Continuously monitor operational KPIs to improve customer satisfaction.
---

# 🚀 How To Use
## Prerequisites
- Microsoft Power BI Desktop (Latest Version)
## Installation
1. Clone this repository.
2. Open the `.pbix` file in Power BI Desktop.
```
Transform Data
    → Data Source Settings
```
4. Refresh the dataset.

5. Explore the dashboard using slicers and interactive visuals.
---

# 📁 Repository Structure
```
Bike-Stations-Sharing-Data/
│
├── Bike Stations Sharing Data.pbix
├── README.md
├── Images/
│   ├── Contract Analysis.png
│   ├── Station Performance.png
│   └── Geographic Analysis.png
└── Dataset/
    └── Bike Sharing Dataset.csv
```
---

# 🛠️ Tools & Technologies

- Microsoft Power BI Desktop
- Power Query
- DAX
- Open Government Data
- Data Modeling
- Interactive Dashboards
---

# 📌 Future Enhancements

- Real-time data integration
- Predictive bike demand forecasting
- Mobile-optimized dashboard
- Automated alerts for empty/full stations
- Weather-based demand analysis
---
# 👤 Author

**Sugantha Vignesh Kumar**

Power BI Developer | Data Analyst
---
