# Seasonal Agriculture Performance Analysis

**VOIS AICTE Batch 1 2026--2027 --- Major Project**

## Project Overview

Agricultural performance is influenced by seasonal variations in
environmental conditions, farming practices, resource availability, and
market conditions. This project analyzes agricultural data across
different seasons to identify meaningful patterns, trends,
relationships, and variations in agricultural performance.

The project focuses on agricultural yield and production, environmental
conditions, soil characteristics, farming practices, resource usage,
water efficiency, economic performance, and disease/pest risk.

The analysis is implemented in **Python using Google Colab**.

## Problem Statement

Raw agricultural data does not clearly explain how agricultural
performance changes across seasons or what patterns can be observed
under different seasonal conditions.

This project investigates seasonal differences in agricultural
performance by identifying: - Seasonal patterns and trends - Differences
in yield and production - Environmental variations - Resource-usage
differences - Relationships between environmental conditions and
agricultural outcomes - Economic differences across seasons - Regional
and crop-level variations - Unusual patterns and observations

## Objectives

1.  Explore and understand the agricultural dataset.
2.  Clean and prepare the data for analysis.
3.  Examine agricultural performance across seasons.
4.  Identify important seasonal patterns and trends.
5.  Compare yield and production across seasons.
6.  Analyze environmental conditions across seasons.
7.  Investigate resource usage and water efficiency.
8.  Analyze relationships between farming practices and agricultural
    performance.
9.  Compare revenue, cost, profit, and profitability across seasons.
10. Examine crop-wise and regional differences.
11. Apply appropriate statistical and visualization techniques.
12. Develop evidence-based conclusions and recommendations.

## Dataset Overview

  Attribute              Details
  -------------------- ---------
  Farm records             4,000
  Variables                   28
  Seasons                      3
  States                       8
  Districts                   10
  Crops                        8
  Irrigation methods           4

### Main Data Categories

-   **Location:** State, District
-   **Agriculture:** Farm area, Crop, Season
-   **Environment:** Rainfall, average temperature, humidity, sunlight
    hours
-   **Soil:** Soil pH, soil moisture
-   **Nutrients:** Nitrogen, phosphorus, potassium
-   **Farming practices:** Irrigation method, fertilizer, pesticide,
    seed quality
-   **Performance:** Yield, production
-   **Economics:** Market price, total cost, revenue, profit
-   **Resources/Risk:** Water used, water efficiency, disease/pest risk

## Analytical Workflow

``` text
Agricultural CSV Dataset
          ↓
Dataset Exploration
          ↓
Data Cleaning & Validation
          ↓
Feature Engineering
          ↓
Exploratory Data Analysis
          ↓
Seasonal Analysis
          ↓
Environmental & Crop Analysis
          ↓
Resource & Irrigation Analysis
          ↓
Economic & Regional Analysis
          ↓
Correlation Analysis
          ↓
Statistical Testing
          ↓
Insights & Recommendations
```

## Data Cleaning

### Missing Values

Missing numerical values were identified in: - `Rainfall_mm` -
`Soil_Moisture_pct` - `Yield_Tonnes_Ha`

These values were handled using **median imputation**.

### Duplicate Records

Duplicate records were checked.

**Duplicate records found: 0**

### Outliers

Outliers were identified using the **Interquartile Range (IQR)** method.
They were not automatically removed because extreme agricultural
observations may represent genuine observations rather than errors.

## Feature Engineering

The following derived variables were created:

-   `Profit_Margin_pct`
-   `Revenue_per_Hectare_INR`
-   `Cost_per_Hectare_INR`
-   `Profit_per_Hectare_INR`
-   `Production_per_Hectare`
-   `Profit_Status`

## Analysis Performed

### Seasonal Performance

Comparison of yield, production, revenue, cost, profit, profit margin,
and water efficiency across Kharif, Rabi, and Zaid.

### Environmental Analysis

Analysis of rainfall, temperature, humidity, sunlight, and soil moisture
across seasons, plus relationships with yield.

### Crop Analysis

Analysis of average yield, production, revenue, profit, and crop ×
season performance.

### Irrigation and Resources

Analysis of water usage, water efficiency, irrigation method vs. yield,
irrigation method vs. water efficiency, fertilizer vs. yield, and seed
quality vs. yield.

### Economic Analysis

Analysis of revenue, total cost, profit, profit margin, profit per
hectare, and profitable vs. loss-making farms.

### Regional Analysis

Comparison across states and state × season combinations.

### Statistical Analysis

-   Pearson correlation
-   Correlation significance tests
-   One-way ANOVA
-   Pairwise seasonal comparisons

## Key Findings

The completed analysis produced these observations:

-   **Kharif** recorded the highest average yield at approximately
    **5.63 tonnes/hectare**.
-   **Kharif** recorded the highest average profit at approximately
    **INR 178,915**.
-   Average profit:
    -   Kharif: **INR 178,915**
    -   Rabi: **INR 87,689**
    -   Zaid: **INR -24,805**
-   Kharif had the highest average rainfall at approximately **849 mm**.
-   Kharif had the highest average soil moisture at approximately
    **31.2%**.
-   Zaid had the highest average temperature at approximately
    **31.0°C**.
-   **Sugarcane** had the highest overall average yield at approximately
    **46.94 tonnes/hectare**.
-   **Rainfed** recorded the highest observed water-efficiency value at
    approximately **7.56 tonnes per 1,000 m³**.
-   **Drip** recorded the highest average profit among irrigation
    methods at approximately **INR 219,626**.
-   There were **2,034 profitable farms** and **1,966 loss-making
    farms**.

### ANOVA Result

A one-way ANOVA tested whether mean yield differs across seasons:

-   F-statistic = **1.544**
-   p-value = **0.214**
-   Significance level = **0.05**

Because p \> 0.05, the analysis does not provide sufficient statistical
evidence to conclude that mean yield differs significantly across the
three seasons.

### Correlation Result

Among the independent variables tested, `Water_Used_m3` had the
strongest positive correlation with yield:

-   **r = 0.386**

`Soil_pH` had the strongest negative correlation among the tested
independent variables:

-   **r = -0.021**

Correlation indicates association and **does not establish causation**.

## Visualizations

The project uses: - Bar charts - Box plots - Histograms - Scatter
plots - Heatmaps - Seasonal comparison charts - Crop × season heatmaps -
Irrigation comparison charts - Economic performance charts -
Profitability charts - Correlation heatmaps

## Technologies Used

  Technology     Purpose
  -------------- ------------------------------------
  Python         Primary programming language
  Google Colab   Notebook and execution environment
  Pandas         Data manipulation and analysis
  NumPy          Numerical computation
  Matplotlib     Data visualization
  Seaborn        Statistical visualization
  SciPy          Statistical analysis
  CSV            Dataset format

## Project Structure

``` text
Seasonal-Agriculture-Performance-Analysis/
│
├── README.md
├── seasonal_agriculture_performance_dataset.csv
├── Seasonal_Agriculture_Performance_Analysis.ipynb
│
├── outputs/
│   ├── charts/
│   └── tables/
│
└── presentation/
    └── Seasonal_Agriculture_Performance_Analysis_VOIS.pptx
```

## How to Run

### Google Colab

1.  Open the project notebook in Google Colab.
2.  Upload the agricultural CSV dataset when prompted.
3.  Run the notebook cells from top to bottom.
4.  Review the generated tables, visualizations, statistical results,
    and findings.

### Local Jupyter Environment

Install the required packages:

``` bash
pip install pandas numpy matplotlib seaborn scipy
```

Then open the notebook:

``` bash
jupyter notebook
```

## Interpretation Notes

### Correlation is not causation

A correlation between two variables does not prove that one causes the
other.

### Outliers

Outliers were identified using IQR but were not automatically removed
because extreme observations may be genuine.

### Water efficiency

Water efficiency is derived from yield and water-use information.
Therefore, its relationship with yield should not be interpreted as an
independent causal effect.

### Statistical significance

Observed differences between seasons are not automatically statistically
significant; the ANOVA result is used to evaluate seasonal yield
differences.

## Limitations

-   The dataset does not establish causal relationships.
-   Analysis is limited to the available observations and variables.
-   Multi-year time-series analysis is not included.
-   Real-time weather and market data are not integrated.
-   Predictive machine-learning models are outside the current scope.
-   Findings should be interpreted within the context of the available
    sample.

## Future Scope

-   Predictive yield modeling using environmental and farming variables
-   Crop recommendation based on seasonal and regional conditions
-   Future yield forecasting using multi-year historical data
-   Geospatial analysis of agricultural performance
-   Interactive Power BI, Tableau, or Streamlit dashboard
-   Integration of real-time weather, soil, market-price, and irrigation
    data

## Project Deliverables

-   Cleaned agricultural dataset
-   Exploratory data analysis
-   Seasonal performance analysis
-   Environmental analysis
-   Crop analysis
-   Resource and irrigation analysis
-   Economic analysis
-   Regional analysis
-   Correlation analysis
-   Statistical hypothesis testing
-   Data visualizations
-   Key insights
-   Recommendations
-   Internship presentation

## Author

**Student Name:** \[Your Name\]

**College:** \[Your College Name\]

**AICTE STU ID:** \[Your AICTE STU ID\]

**Program:** VOIS AICTE Batch 1 2026--2027

**Project:** Seasonal Agriculture Performance Analysis

**GitHub:** \[Insert GitHub Repository Link\]

## Acknowledgement

This project was completed as part of the **VOIS AICTE Batch 1
2026--2027 Major Project** and applies data analytics techniques to
investigate seasonal agricultural performance and derive evidence-based
insights from the provided dataset.
