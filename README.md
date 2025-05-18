# Bangladesh Weather Analysis (1901-2015)

## 🌍 Project Overview
Analysis of long-term temperature and rainfall patterns in Bangladesh using NASA climate data and humanitarian datasets. This project demonstrates:

- **Data Wrangling**: Cleaned and merged multi-source climate data with 98% completeness
- **Time-Series Analysis**: Identified century-long trends using SQL window functions
- **Impact Visualization**: Dashboard reveals climate risks to agriculture and infrastructure

## 📊 Data Sources
### Primary Datasets
#### 🌡️ Temperature Data
- **Source**: [NASA POWER](https://power.larc.nasa.gov/data-access-viewer/)  
- **Coverage**: Monthly averages (1901–2015) at 0.5° × 0.5° resolution  
- **Variables**: Surface temperature (°C), anomalies  

#### 🌧️ Rainfall Data 
- **Source**: [HDX Bangladesh Rainfall](https://data.humdata.org/dataset/bangladesh-rainfall-data)  
- **License**: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)  
- **Key Metrics**: Precipitation (mm), dry/wet spell frequency  

*Processed using BigQuery ([see pipeline](sql/1_data_cleaning.sql)).*

## 🔍 Key Insights
- **Warming Trend**: +1.2°C mean temperature rise since 1901, accelerating post-1980 (+0.3°C/decade)  
- **Monsoon Shifts**: 15% increase in July rainfall volatility since 1950  
- **Seasonal Compression**: Winter months (Dec-Feb) warmed 2.1× faster than summer months  
- **Extreme Events**: 3σ rainfall events became 40% more frequent after 1990  

## 📂 Repository Structure
```
bangladesh-weather-analysis/
├── data/               # Raw/processed CSVs
│   ├── raw_nasa.csv
│   └── cleaned_merged.csv
├── sql/                # Transformation scripts
│   ├── 1_data_cleaning.sql
│   └── 2_trend_analysis.sql
└── visualizations/     # Exports
    ├── dashboard.png
    └── correlation_heatmap.png
```
## 🛠️ Technical Implementation
- **Data Processing**: BigQuery SQL (CTEs, window functions)  
- **Visualization**: Tableau (dual-axis charts, parameter controls)  
- **Analysis**: 5-year moving averages, YoY change calculations  

## 🚀 How to Replicate
  **Run SQL scripts** in order:

   ```sql
   -- In BigQuery:
   EXECUTE IMMEDIATE FROM 'sql/1_data_cleaning.sql';
   ```sql

Visualize: Import data/cleaned_merged.csv into Tableau
   Explore: Interact with Tableau Public Dashboard  ```

