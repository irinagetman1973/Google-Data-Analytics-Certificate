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
2. - **Temperature Consistency Check**:
   -  Verified if the Celsius and Fahrenheit temperatures match. The formula used: `=IF(ROUND((C2*9/5+32),2)=ROUND(H2,2), "Match", "Check")`.

- Exploratory Data Analysis (EDA)
- Statistical Analysis
- Data Visualization

## Analysis Files
- **Data Cleaning:** [lettuce_data_cleaning.xlsx](lettuce_data_cleaning.xlsx)
- **Exploratory Analysis:** [lettuce_exploratory_analysis.xlsx](lettuce_exploratory_analysis.xlsx)
- **Visualizations:** [lettuce_visualizations.xlsx](lettuce_visualizations.xlsx)

## Results
- [Lettuce Growth Analysis Report](../../reports/lettuce_analysis_report.pdf)

## Visuals
![Lettuce Growth Chart](../../images/lettuce_growth_chart.png)

## Detailed Description
This project involves analyzing the lettuce growth dataset to understand the impact of various factors such as temperature, humidity, and pH levels on the growth of lettuce. The analysis includes data cleaning, exploratory data analysis, and visualization of the key findings.

