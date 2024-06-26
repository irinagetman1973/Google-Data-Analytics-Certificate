# Lettuce Growth Data Analysis

![Lettuce](../../images/dataset-cover.jpg)

## Objective
Analyze the factors affecting lettuce growth and provide insights for optimizing growth conditions.

## Dataset
- **Source:** [Lettuce Growth Days Dataset on Kaggle](https://www.kaggle.com/datasets/jjayfabor/lettuce-growth-days)
- **File:** [lettuce_dataset.csv](../../datasets/lettuce_dataset_updated.csv)


## Tasks
### Data Cleaning Process
1. **Date Normalization**:
   - The original date column contained dates in inconsistent formats.
   - A formula was applied to normalize all dates to the `MM/DD/YYYY` format.
   - The normalized dates were copied back to the original date column to maintain consistency.
2. **Temperature Consistency Check**:
   -  Verified if the Celsius and Fahrenheit temperatures match. The formula used: `=IF(ROUND((C2*9/5+32),2)=ROUND(H2,2), "Match", "Check")`.

### Exploratory Data Analysis (EDA)

- **Summary Statistics**:
  - Mean Temperature: `=AVERAGE('lettuce_dataset_cleaned.csv'!C2:C)`
  - Median Humidity: `=MEDIAN('lettuce_dataset_cleaned.csv'!E2:E)`
  - Min/Max pH Level: `=MIN('lettuce_dataset_cleaned.csv'!F2:F)` / `=MAX('lettuce_dataset_cleaned.csv'!F2:F)`
  - Standard Deviation Temp: `=STDEV(lettuce_dataset_cleaned.csv!C2:C)`
  - Variance Humidity: `=VAR('lettuce_dataset_cleaned.csv'!D2:D)`
  - Corr (Temp, Growth Days):	 `=CORREL('lettuce_dataset_cleaned.csv'!C2:C, 'lettuce_dataset_cleaned.csv'!G2:G)`
- **Visualizations**:
   - Scatter Plot of Growth Days vs Temperature (°C)
  
   ![Scatter Plot](../../images/Growth%20Days%20vs%20Temperature%20(°C).png)
  - Histogram of Humidity (%)
    
  ![Histogram Plot](../../images/Histogram%20of%20Humidity%20(%25).png)

### Feature Engineering



1. **Max Growth Days**:
    - **Column Added**: `Max Growth Days`
    - **Formula**: `=MAXIFS($D$2:$D$3170, $A$2:$A$3170, A2)`
    - `Max Growth Days` captures the longest period each plant has grown.

2. **Average TDS Value**:
    - **Column Added**: `Avg TDS Value`
    - **Formula**: `=IFERROR(AVERAGEIFS($E$2:$E$3170, $A$2:$A$3170, A2), "N/A")`
    - `Avg TDS Value` provides the average nutrient concentration for each plant during its growth period.
3. **Normalized pH Level**:
    - **Column Added**: `Normalized pH`
    - **Formula**: `=(F2 - MIN(F:F)) / (MAX(F:F) - MIN(F:F))`
    - This formula normalizes the pH level to a 0-1 scale.

4. **Average pH Level**:
    - **Column Added**: `Avg pH`
    - **Formula**: `=AVERAGEIFS($F$2:$F$3170, $A$2:$A$3170, A2)`
    - This formula calculates the average pH level for each plant.

5. **Average Temperature**:
    - **Column Added**: `Avg Temperature`
    - **Formula**: `=AVERAGEIFS($C$2:$C$3170, $A$2:$A$3170, A2)`
    - This formula calculates the average temperature for each plant over the growth period.

6. **Temperature Range**:
    - **Column Added**: `Temp Range`
    - **Formula**: `=MAXIFS($C$2:$C$3170, $A$2:$A$3170, A2) - MINIFS($C$2:$C$3170, $A$2:$A$3170, A2)`
    - This formula calculates the difference between the maximum and minimum temperatures recorded for each plant.

7. **Average Humidity**:
    - **Column Added**: `Avg Humidity`
    - **Formula**: `=AVERAGEIFS($I$2:$I$3170, $A$2:$A$3170, A2)`
    - This formula calculates the average humidity for each plant over the growth period.



### Example of Added Columns

| Plant_ID | Date       | Temperature (°C) | Humidity (%) | TDS Value (ppm) | pH Level | Growth Days | Max Growth Days | Avg TDS Value | Growth Rate | Normalized pH | Avg pH | Avg Temperature | Temp Range |
|----------|------------|------------------|--------------|-----------------|----------|-------------|-----------------|---------------|-------------|---------------|--------|-----------------|-------------|
| 1        | 09/01/2023 | 30.2             | 65           | 650             | 6.5      | 45          | 48              | 663           | 0.94        | 0.81          | 6.4    | 30.25           | 1.8         |
| 1        | 09/02/2023 | 30.3             | 66           | 660             | 6.4      | 46          | 48              | 663           | 0.96        | 0.79          | 6.4    | 30.25           | 1.8         |
| 2        | 09/01/2023 | 30.1             | 64           | 670             | 6.3      | 45          | 47              | 680           | 0.96        | 0.76          | 6.35   | 30.15           | 2.1         |
| 2        | 09/02/2023 | 30.2             | 65           | 675             | 6.4      | 46          | 47              | 680           | 0.98        | 0.79          | 6.35   | 30.15           | 2.1         |






### Statistical Analysis

1. **Summary Statistics**:
   - Calculated mean, median, and standard deviation for key features like temperature, humidity, pH level, and TDS value.

2. **Correlation Analysis**:
   - Determined the correlations between different features to understand their relationships.
   - **Correlation between Temperature and Growth Days**: `=CORREL(C2:C3170, G2:G3170)`
   - **Correlation between Humidity and Growth Days**: `=CORREL(D2:D3170, G2:G3170)`
   - **Correlation between pH Level and Growth Days**: `=CORREL(F2:F3170, G2:G3170)`
   - **Correlation between TDS Value and Growth Days**: `=CORREL(E2:E3170, G2:G3170)`

### Visualization and Reporting

- Interactive dashboards were created to present key insights.
- A final report summarizing the analysis, findings, and recommendations was prepared.


## Analysis Files
- **Data Cleaning & Feature Engineering** [lettuce_data_cleaning.xlsx](lettuce_data_cleaning.xlsx)
- **Exploratory Analysis:** [lettuce_exploratory_analysis.xlsx](lettuce_exploratory_analysis.xlsx)
- **Visualizations:** [lettuce_visualizations.xlsx](lettuce_visualizations.xlsx)

## Results
- [Lettuce Growth Analysis Report](../../reports/lettuce_analysis_report.pdf)

## Visuals
![Lettuce Growth Chart](../../images/lettuce_growth_chart.png)

## Detailed Description
This project involves analyzing the lettuce growth dataset to understand the impact of various factors such as temperature, humidity, and pH levels on the growth of lettuce. The analysis includes data cleaning, exploratory data analysis, and visualization of the key findings.

