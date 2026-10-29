# Telecom Customer Churn & Retention Analytics

An end-to-end data analytics project using Python, Pandas, MySQL, and Power BI to analyze telecom customer churn and identify customer segments that may need improved retention strategies.

## 📌 Project Overview

Customer churn occurs when customers stop using a company's services. This project analyzes telecom customer data to understand churn patterns across contract types, customer tenure, payment methods, internet services, and technical support.

The workflow includes data cleaning, exploratory data analysis, SQL queries, and an interactive Power BI dashboard.

## 🛠️ Tools & Technologies

- **Python** — data preparation and analysis
- **Pandas** — data cleaning and manipulation
- **Jupyter Notebook** — analysis workflow
- **Matplotlib** — data visualization
- **MySQL** — SQL analysis
- **Power BI Desktop** — interactive dashboard

## 📂 Dataset

The project uses IBM's public Telco Customer Churn sample dataset.

- **Customer records:** 7,043
- **Columns:** 21
- **Target variable:** `Churn`

Dataset source: [IBM Telco Customer Churn CSV](https://raw.githubusercontent.com/IBM/telco-customer-churn-on-icp4d/master/data/Telco-Customer-Churn.csv)

## 📊 Key Performance Indicators

| Metric | Result |
|---|---:|
| Total Customers | 7,043 |
| Churned Customers | 1,869 |
| Retained Customers | 5,174 |
| Overall Churn Rate | 26.54% |

## 🔍 Key Business Insights

### Contract Type

| Contract | Churn Rate |
|---|---:|
| Month-to-month | 42.71% |
| One year | 11.27% |
| Two year | 2.83% |

Month-to-month customers have the highest observed churn rate.

### Customer Tenure

| Tenure Group | Churn Rate |
|---|---:|
| 0–12 months | 47.44% |
| 13–24 months | 28.71% |
| 25–48 months | 20.39% |
| 49–72 months | 9.51% |

Customers in their first year have the highest observed churn rate, making early engagement an important area to investigate.

### Payment Method

| Payment Method | Churn Rate |
|---|---:|
| Electronic check | 45.29% |
| Mailed check | 19.11% |
| Bank transfer (automatic) | 16.71% |
| Credit card (automatic) | 15.24% |

Electronic-check users have the highest observed churn rate among the payment methods analyzed.

### Internet Service

| Service | Churn Rate |
|---|---:|
| Fiber optic | 41.89% |
| DSL | 18.96% |
| No internet service | 7.40% |

Fiber-optic customers have the highest observed churn rate among the internet service groups.

### Technical Support

Customers without technical support have a churn rate of 41.64%, compared with 15.17% for customers with support.

*These findings describe associations in the sample dataset; they do not independently establish the causes of churn.*

## 📈 Power BI Dashboard

The interactive dashboard includes:

- Total Customers KPI
- Churned Customers KPI
- Overall Churn Rate KPI
- Churn Rate by Contract Type
- Churn Rate by Tenure Group
- Churn Rate by Payment Method
- Churn Rate by Internet Service
- Churn Rate by Technical Support
- Interactive Contract slicer

The contract slicer allows users to filter the dashboard and explore customer segments.

## 🧹 Data Cleaning

The data preparation process included:

- Inspecting data types and missing values
- Checking duplicate rows and customer IDs
- Converting `TotalCharges` to a numeric column
- Handling 11 blank `TotalCharges` values for customers with zero tenure
- Removing unnecessary whitespace from text values
- Exporting the cleaned dataset

Validation results: 7,043 rows preserved, zero duplicate customer IDs, and zero missing values remaining after cleaning.

## 📁 Project Structure

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
├── sql/
│   └── telco_churn_analysis.sql
└── README.md
```

## 🚀 How to Explore

1. Review the raw and cleaned CSV files in `data/`.
2. Open `notebooks/01_Data_Cleaning.ipynb` in VS Code or Jupyter Notebook.
3. Run the SQL queries in `sql/telco_churn_analysis.sql` using MySQL Workbench after importing the cleaned CSV.
4. Open `dashboard/Telco_Customer_Churn_Analytics.pbix` in Power BI Desktop.
5. Use the Contract slicer to explore the dashboard.

## 💡 Business Recommendations

- Investigate onboarding and early engagement for new customers.
- Evaluate retention strategies for month-to-month customers.
- Review the billing experience of electronic-check users.
- Investigate service quality and support needs among fiber-optic customers.
- Track churn KPIs over time to evaluate retention initiatives.

## 📝 Project Summary

This project demonstrates an end-to-end analytics workflow covering data cleaning, exploratory analysis, SQL querying, KPI development, and interactive dashboard design.

It showcases practical skills in Python, Pandas, MySQL, Power BI, data visualization, and business insight communication.

## ⚠️ Disclaimer

This project uses a public sample dataset for educational and portfolio purposes. Results reflect the provided dataset and should not automatically be generalized to all telecom companies.