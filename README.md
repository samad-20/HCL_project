# Bank Customer Data Analysis

## Project Overview
This project explores a bank customer dataset using Python and data analysis libraries.
The aim is to understand customer distribution, account preferences, and banking-channel usage.
It also compares average monthly balances across employment categories.
The analysis is intended for learning and exploratory data analysis (EDA).
The results describe only the supplied dataset and are not official bank-wide statistics.

## Student Details
- **Name:** Samad Ahmad
- **Admission Number:** 2026b01011054
- **Email:** samad.26b01011054@abes.ac.in
- **Branch / Section:** CSE / 12
- **GitHub Repository:** https://github.com/samad-20/HCL_project
- **Project Date:** 22-11-2026

## Dataset Information
- **Input file:** `bank_data(4).csv`
- **Dataset format:** CSV (comma-separated values)
- **Rows in source file:** 255
- **Columns in source file:** 12
- **Unique customer IDs:** 250
- **Exact duplicate rows:** 5
- **Missing values:** Present in four columns
- **Date field:** `Last_Review_Date`
- **Date range:** 2024-11-23 to 2026-11-18

## Columns in the Dataset
| Column | Description |
|---|---|
| `Customer_ID` | Customer reference identifier |
| `City` | City associated with the customer |
| `Account_Type` | Type of bank account |
| `Employment_Type` | Customer employment category |
| `Preferred_Channel` | Customer's preferred banking channel |
| `Age` | Customer age in years |
| `Monthly_Income` | Customer monthly income |
| `Tenure_Years` | Years the customer has been with the bank |
| `Monthly_Transactions` | Number of monthly transactions |
| `Branch_Visits` | Number of bank branch visits |
| `Last_Review_Date` | Date of the latest customer review |
| `Avg_Monthly_Balance` | Average monthly account balance |

## Tools and Technologies
- **Python:** Main programming language.
- **pandas:** Reading, cleaning, grouping, and summarising data.
- **NumPy:** Numerical operations and calculations.
- **Matplotlib:** Creating data visualisations.
- **Seaborn:** Optional statistical chart styling.
- **Jupyter Notebook:** Running the analysis step by step.
- **Visual Studio Code:** Editing project files and notebooks.
- **Git and GitHub:** Version control and project sharing.

## Project Objectives
1. Find the number of customers in each city.
2. Identify the most preferred banking channel.
3. Understand the distribution of account types.
4. Compare average monthly balance by employment type.
5. Inspect missing values, duplicate records, and inconsistent text.
6. Create clear tables and charts to communicate the results.

## Business Questions
### 1. Which cities have the highest number of customers?
The city field is standardised before grouping.
The source values include inconsistent spaces and capitalisation.
After standardisation, Mumbai has 72 records.
Delhi has 67 records.
Bengaluru has 46 records.
Lucknow has 36 records.
Ghaziabad has 34 records.
These counts are calculated on the original 255-row file before removing exact duplicate rows.

### 2. Which banking channel is most preferred?
`Preferred_Channel` is counted using its category values.
Mobile App has 119 records.
Net Banking has 67 records.
Branch has 43 records.
ATM has 26 records.
Mobile App is the most frequently recorded preferred channel in this file.
The counts above are from the original source dataset.

### 3. What is the distribution of account types?
Savings accounts have 122 records.
Salary accounts have 73 records.
Current accounts have 34 records.
Joint accounts have 26 records.
Savings is the most common account category in this dataset.
The counts above are from the original source dataset.

### 4. How does average balance vary by employment type?
The comparison uses the mean of `Avg_Monthly_Balance`.
Salaried customers have an average balance of approximately 58,738.58.
Self-employed customers have an average balance of approximately 59,030.00.
Retired customers have an average balance of approximately 62,692.59.
Students have an average balance of approximately 54,734.62.
Five records have a missing employment category and are not included in these group means.
These figures are descriptive averages, not recommendations about individual customers.

## Data Quality Checks
The source file contains 255 rows and 12 columns.
There are 5 exact duplicate rows.
There are 5 repeated customer ID occurrences.
There are 5 missing values in `Employment_Type`.
There are 5 missing values in `Monthly_Income`.
There are 5 missing values in `Tenure_Years`.
There are 6 missing values in `Monthly_Transactions`.
The `City` column contains 7 entries with inconsistent case or extra spaces.
The `Age` column contains two implausible values: -27 and 212.
The age values should be validated rather than silently accepted.
Missing values should be handled using a documented rule.
Numeric median imputation may be considered after checking each distribution.
Missing employment categories may be retained as `Unknown` or filled only when justified.
Exact duplicates should be removed before producing final summaries.
Repeated customer IDs should be checked so records are not accidentally discarded.
The original raw CSV should remain unchanged.

## Suggested Cleaning Plan
1. Load the source CSV with pandas.
2. Inspect shape, data types, and descriptive statistics.
3. Count missing values in every column.
4. Identify exact duplicate rows.
5. Review repeated values in `Customer_ID`.
6. Remove confirmed exact duplicate rows.
7. Strip leading and trailing spaces from text fields.
8. Standardise city names consistently.
9. Validate age values against a documented acceptable range.
10. Decide and document how missing values will be handled.
11. Convert `Last_Review_Date` to a datetime type.
12. Recheck the cleaned data before analysis.
13. Save the cleaned file separately from the raw file.

## Suggested Derived Columns
- `Age_Group`: age band created from validated age values.
- `Income_Band`: monthly income category.
- `Tenure_Category`: customer tenure category in years.
The exact band boundaries should be stated in the notebook.
Invalid or missing source values should not be assigned misleading categories.
Derived columns are created for analysis and do not replace original fields.

## Visualisations to Create
- Bar chart: customer count by city.
- Bar chart: preferred banking channel.
- Bar chart: account type distribution.
- Bar chart: average monthly balance by employment type.
- Optional chart: age-group distribution after age validation.
- Optional chart: monthly transactions by preferred channel.
Each chart should have a clear title and labelled axes.
Charts should be saved in the `images/` directory.
Chart values must match the summary tables in the notebook.


## Project Directory Structure

The project is organised into the following folders and files:

```text
DATA_ANALYTICS_PROJECT/
├── data/
│   ├── processed/
│   │   └── bank_data_cleaned.csv
│   └── raw/
│       └── bank_data.csv
├── images/
│   ├── 01_customer_distribution_by_city.png
│   ├── 02_account_type_distribution.png
│   ├── 03_employment_type_distribution.png
│   ├── 04_preferred_banking_channel.png
│   ├── 05_age_distribution.png
│   ├── 06_monthly_income_distribution.png
│   ├── 07_average_balance_by_city.png
│   ├── 08_monthly_transactions_distribution.png
│   └── 09_correlation_heatmap.png
├── notebooks/
│   └── draft.ipynb
├── script/
│   ├── Presentation.pptx
│   └── SRS.docx
├── README.md
└── requirement.txt
```
