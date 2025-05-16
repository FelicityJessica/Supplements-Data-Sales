#  Supplement Sales Data Analysis (2020–2025)

![Image](https://github.com/user-attachments/assets/cb3d7134-c8bd-474f-ac19-3ff638dc39ba)
## Introduction
This project presents an in-depth analysis of weekly supplement sales data between 2020 and 2025. The analysis explores revenue trends, product category performance, platform comparisons, and how price, discount, and units sold affect revenue using Excel (with Power Pivot and regression tools) and Power BI.

---

##  Dataset Overview

- **Period Covered:** 2020 to 2025  
- **Sales Platforms:** Amazon, Walmart, iHerb  
- **Locations:** USA, UK, Canada  
- **Product Categories:** Protein, Vitamin, Omega, Amino Acid, Fat Burner, Herbal, Mineral, Performance, Sleep Aid, Hydration  
- **Metrics:** Units Sold, Price, Discount, Revenue

---

##  Business Questions Answered

1. How has revenue changed over time?
2. Which product categories generate the highest revenue?
3. What are the average units sold and revenue per platform?
4. What is the relationship between units sold and revenue?
5. How do units sold, price, and discount together affect revenue?

---

##  Tools & Techniques Used

- **Excel**
  - Power Pivot for data modeling
  - PivotTables and Slicers
  - Charts and regression tools (Data Analysis Toolpak)
- **Power BI**
  - Visualizations and dashboards
  - Slicers and Decomposition Tree

---

##  Visualizations Used

| Question | Tool      | Chart Type               | Slicers/Filters Used                             |
|----------|-----------|--------------------------|--------------------------------------------------|
| Q1       | Excel & Power BI | Line Chart               | Excel slicers for Platform and Year (Power Pivot) |
| Q2       | Excel & Power BI | Pie Chart               | None                                             |
| Q3       | Excel & Power BI | Clustered Column Chart   | None                                             |
| Q4       | Excel              | Scatter Plot + Trendline | None                                             |
| Q5       | Power BI           | Decomposition Tree       | Slicers for Platform, Location, Category, Date   |

---

##  Key Findings

- **Revenue Growth** peaked in 2023 at $4.47M.
- **Top Categories**:
  - Vitamins: $4.30M  
  - Minerals: $4.27M  
- **Platform Averages**:
  - iHerb had the highest average revenue and units sold per record.
- **Units Sold vs Revenue**:
  - Weak correlation in single-variable model.
  - Very strong correlation when combined with price and discount.

---

##  Regression Analysis

###  Question 4: Single Linear Regression  
**Target Variable:** Revenue  
**Predictor:** Units Sold  

**Regression Summary Table**:

| Metric                 | Value         |
|------------------------|---------------|
| R Square               | 0.0443        |
| Adjusted R Square      | 0.0441        |
| Standard Error         | 2143.87       |
| Observations           | 4,383         |
| F-statistic            | 202.99        |
| Significance F         | 4.66E-45      |

**Coefficients**:

| Term       | Coefficient | Std. Error | t Stat   | P-value    | 95% CI Lower | 95% CI Upper |
|------------|-------------|------------|----------|------------|---------------|---------------|
| Intercept  | -363.82     | 393.72     | -0.92    | 0.356      | -1135.72      | 408.08        |
| Units Sold | 37.22       | 2.61       | 14.25    | 4.66E-45   | 32.10         | 42.34         |

**Conclusion:**  
There is a statistically significant, but weak, positive relationship between units sold and revenue (R² = 0.0443).

---

###  Question 5: Multiple Linear Regression  
**Target Variable:** Revenue  
**Predictors:** Units Sold, Price, Discount  

**Regression Summary Table**:

| Metric                 | Value         |
|------------------------|---------------|
| R Square               | 0.9937        |
| Adjusted R Square      | 0.9937        |
| Standard Error         | 173.42        |
| Observations           | 4,384         |
| F-statistic            | 232,057.70    |
| Significance F         | 0             |

**Coefficients**:

| Term       | Coefficient  | Std. Error | t Stat     | P-value | 95% CI Lower | 95% CI Upper |
|------------|--------------|------------|------------|---------|---------------|---------------|
| Intercept  | -5234.12     | 32.78      | -159.69    | 0.000   | -5298.37       | -5169.86       |
| Units Sold | 34.85        | 0.21       | 164.90     | 0.000   | 34.44          | 35.27          |
| Price      | 150.48       | 0.18       | 815.52     | 0.000   | 150.12         | 150.84         |
| Discount   | -61.95       | 36.49      | -1.70      | 0.090   | -133.49        | 9.59           |

**Conclusion:**  
The model explains 99.37% of the variation in revenue. Units sold and price are strong, significant predictors. Discount has a negative but not statistically significant effect at 95% confidence.

---

##  Slicer & Interaction Usage

### In **Excel**:
- **Q1** used slicers for:
  - Platform
  - Year  
- Powered by **Power Pivot** model for dynamic interaction.

### In **Power BI**:
- **Q5** used:
  - Decomposition Tree
  - Slicers for Platform, Location, Category, Date (Month/Year)  
- Enabled drill-down exploration of revenue patterns across multiple dimensions.

---

##  File Structure

- `Excel_Analysis.xlsx` — Contains raw data, PivotTables, charts, slicers, and regression analysis  
- `PowerBI_Report.pbix` — Interactive dashboard including decomposition tree and filters  
- `README.md` — Full documentation of the project

---

##  Conclusion

This project delivers a comprehensive analysis of supplement sales across different platforms and regions, with insights into revenue patterns and the underlying drivers of performance. Both Excel (including Power Pivot and regression) and Power BI were used to present visual and statistical findings.

---
