# Telecom Customer Churn & Retention Analytics

## 1. Project Overview

This project analyzes customer churn in the telecommunications industry using Python, Pandas, MySQL, and Power BI.

Customer churn occurs when customers stop using a company's services. Understanding churn patterns helps businesses identify customer segments that may require better onboarding, service improvements, and retention strategies.

The project follows an end-to-end data analytics workflow, including data cleaning, exploratory data analysis (EDA), SQL analysis, interactive dashboard development, and business recommendations.

## 2. Project Objectives

The main objectives are:

- Clean and validate the telecom customer dataset.
- Calculate customer churn KPIs.
- Analyze churn across contract types, tenure groups, payment methods, internet services, and technical support.
- Use SQL to answer business questions.
- Build an interactive Power BI dashboard.
- Communicate findings through actionable business recommendations.

## 3. Tools and Technologies

| Tool | Purpose |
|---|---|
| Python | Data preparation and analysis |
| Pandas | Data cleaning and manipulation |
| Jupyter Notebook | Analysis workflow |
| Matplotlib | Data visualization |
| MySQL | SQL queries and customer segmentation |
| Power BI Desktop | Interactive dashboard |
| Markdown | Project documentation |

## 4. Dataset Description

The project uses IBM's public Telco Customer Churn sample dataset.

**Dataset source:** [IBM Telco Customer Churn CSV](https://raw.githubusercontent.com/IBM/telco-customer-churn-on-icp4d/master/data/Telco-Customer-Churn.csv)

The original dataset contains 7,043 customer records and 21 columns.

Important fields include:

- `customerID` — unique customer identifier
- `gender` — customer gender
- `SeniorCitizen` — senior-citizen indicator
- `tenure` — number of months with the company
- `Contract` — contract type
- `PaymentMethod` — payment method
- `InternetService` — internet service type
- `TechSupport` — technical support subscription
- `MonthlyCharges` — monthly customer charges
- `TotalCharges` — total customer charges
- `Churn` — whether the customer left the company

## 5. Data Cleaning

Data cleaning was performed in `notebooks/01_Data_Cleaning.ipynb` using Python and Pandas.

The steps included:

1. Loading and inspecting the raw CSV dataset.
2. Checking column names, data types, and missing values.
3. Checking for duplicate records and duplicate customer IDs.
4. Identifying 11 blank values in `TotalCharges`.
5. Converting `TotalCharges` to a numeric data type.
6. Replacing blank `TotalCharges` values with zero for customers whose tenure was zero.
7. Removing unnecessary leading and trailing whitespace from text fields.
8. Saving the cleaned dataset as a CSV file.

### Cleaning Validation

| Validation | Result |
|---|---:|
| Original records | 7,043 |
| Cleaned records | 7,043 |
| Columns | 21 |
| Duplicate customer IDs | 0 |
| Missing values after cleaning | 0 |
| Blank `TotalCharges` values after cleaning | 0 |

All 7,043 records were preserved during cleaning.

## 6. Key Performance Indicators

The analysis produced the following overall metrics:

| KPI | Result |
|---|---:|
| Total Customers | 7,043 |
| Churned Customers | 1,869 |
| Retained Customers | 5,174 |
| Overall Churn Rate | 26.54% |

The churn rate was calculated as:

**Churn Rate = (Churned Customers / Total Customers) × 100**

The resulting churn rate indicates that approximately 26.54% of the customers in this dataset had churned.

## 7. Exploratory Data Analysis

Exploratory analysis examined how churn varies across customer groups.

### 7.1 Churn by Contract Type

| Contract Type | Total Customers | Churned Customers | Churn Rate |
|---|---:|---:|---:|
| Month-to-month | 3,875 | 1,655 | 42.71% |
| One year | 1,473 | 166 | 11.27% |
| Two year | 1,695 | 48 | 2.83% |

**Finding:** Month-to-month customers have the highest observed churn rate, while customers on two-year contracts have the lowest.

### 7.2 Churn by Customer Tenure

| Tenure Group | Total Customers | Churned Customers | Churn Rate |
|---|---:|---:|---:|
| 0–12 months | 2,186 | 1,037 | 47.44% |
| 13–24 months | 1,024 | 294 | 28.71% |
| 25–48 months | 1,594 | 325 | 20.39% |
| 49–72 months | 2,239 | 213 | 9.51% |

**Finding:** Customers in their first year have the highest observed churn rate. Churn rates decrease across the longer-tenure groups.

### 7.3 Churn by Payment Method

| Payment Method | Total Customers | Churned Customers | Churn Rate |
|---|---:|---:|---:|
| Electronic check | 2,365 | 1,071 | 45.29% |
| Mailed check | 1,612 | 308 | 19.11% |
| Bank transfer (automatic) | 1,544 | 258 | 16.71% |
| Credit card (automatic) | 1,522 | 232 | 15.24% |

**Finding:** Electronic-check users have the highest observed churn rate among the payment-method groups.

### 7.4 Churn by Internet Service

| Internet Service | Total Customers | Churned Customers | Churn Rate |
|---|---:|---:|---:|
| Fiber optic | 3,096 | 1,297 | 41.89% |
| DSL | 2,421 | 459 | 18.96% |
| No internet service | 1,526 | 113 | 7.40% |

**Finding:** Fiber-optic customers have the highest observed churn rate among the internet-service groups.

### 7.5 Churn by Technical Support

| Technical Support | Churn Rate |
|---|---:|
| No | 41.64% |
| Yes | 15.17% |
| No internet service | 7.40% |

**Finding:** Customers without technical support have a higher observed churn rate than customers with support.

### 7.6 Churned vs. Retained Customers

| Metric | Retained Customers | Churned Customers |
|---|---:|---:|
| Average tenure | 37.57 months | 17.98 months |
| Median tenure | 38 months | 10 months |
| Average monthly charges | 61.27 | 74.44 |
| Average total charges | 2,549.91 | 1,531.80 |

**Finding:** Churned customers have a shorter average tenure and higher average monthly charges. Their lower average total charges are consistent with their shorter time as customers.

## 8. SQL Analysis

MySQL was used to independently validate key findings and segment customer churn.

The SQL analysis included:

- Overall churn distribution and customer percentages.
- Churn rates by contract type.
- Churn rates by tenure group.
- Churn rates by payment method.
- Churn rates by internet service.

The queries use SQL aggregations, `COUNT`, conditional `SUM`, `CASE WHEN`, `GROUP BY`, and percentage calculations.

The principal results from SQL aligned with those calculated in Python.

## 9. Power BI Dashboard

The interactive dashboard was created in Power BI Desktop and saved as:

`dashboard/Telco_Customer_Churn_Analytics.pbix`

The dashboard includes:

- Total Customers KPI card
- Churned Customers KPI card
- Churn Rate KPI card
- Churn Rate by Contract Type chart
- Churn Rate by Tenure Group chart
- Churn Rate by Payment Method chart
- Churn Rate by Internet Service chart
- Churn Rate by Technical Support chart
- Interactive Contract slicer

The slicer allows users to select contract types and explore how the selected group affects report metrics and charts.

## 10. Business Insights

The analysis highlights several patterns that are relevant to customer retention:

1. Month-to-month customers have a higher churn rate than customers on longer contracts.
2. Customers in their first year have the highest observed churn rate.
3. Electronic-check users have the highest churn rate among the payment methods analyzed.
4. Fiber-optic customers have a higher observed churn rate than DSL customers.
5. Customers without technical support have a higher observed churn rate than customers with support.
6. Churned customers have shorter average tenure and higher average monthly charges than retained customers.

These results identify customer segments that could benefit from further investigation.

## 11. Business Recommendations

Based on the observed patterns, the following actions could be evaluated:

- Improve onboarding and early engagement for new customers.
- Investigate retention offers and contract options for month-to-month customers.
- Review billing experience and payment preferences among electronic-check users.
- Investigate pricing, service quality, and customer expectations among fiber-optic users.
- Evaluate customer support availability and resolution quality.
- Monitor churn KPIs regularly to assess whether retention initiatives are associated with improvements.

These are recommendations for further investigation rather than proof that any single factor causes churn.

## 12. Project Files

The project is organized as follows:

```text
telco_customer_churn_project/
├── dashboard/
│   └── Telco_Customer_Churn_Analytics.pbix
├── data/
│   ├── raw/
│   │   └── Telco-Customer-Churn.csv
│   └── processed/
│       └── Telco-Customer-Churn-Cleaned.csv
├── notebooks/
│   └── 01_Data_Cleaning.ipynb
├── report/
│   └── Telco_Customer_Churn_Analysis_Report.md
├── sql/
│   └── telco_churn_analysis.sql
└── README.md
```

## 13. Conclusion

This project demonstrates an end-to-end data analytics workflow, from data cleaning and exploratory analysis to SQL validation and interactive Power BI reporting.

It showcases practical skills in Python, Pandas, MySQL, data visualization, KPI development, dashboard design, and communicating business insights.

The results provide a starting point for further investigation into customer retention strategies.

## 14. Disclaimer

This project uses a public sample dataset for educational and portfolio purposes. The findings reflect the dataset analyzed and should not automatically be generalized to all telecommunications businesses.

The observed relationships are descriptive and do not independently establish causal factors behind customer churn.