# Retail Banking Customer Behaviour and Average Monthly Balance Analysis

## Student & Project Details
- **Name:** Samad Ahmad[cite: 3]
- **Admission No:** 2026b01011054[cite: 3]
- **Email ID:** samad.26b01011054@abes.ac.in[cite: 3]
- **Branch / Section:** CSE 12[cite: 3]
- **GitHub Repository:** https://github.com/samad-20/HCL_project.git[cite: 3]
- **Date:** 22-11-2026[cite: 3]

## 1. Business Problem
Retail banking teams need to understand how customer demographics (`Age`, `City`, `Employment_Type`), account structures (`Account_Type`), relationship tenure (`Tenure_Years`), income (`Monthly_Income`), and banking channels (`Preferred_Channel`) relate to `Avg_Monthly_Balance`, `Monthly_Transactions`, and `Branch_Visits`[cite: 3]. Clear insights help management identify high-value segments, support customer retention, and guide digital channel adoption[cite: 3].

## 2. Project Folder Structure
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
│   └── srs_document
├── README.md
└── requirement.txt
```[cite: 19]

## 3. Dataset & Data Cleaning Summary
- **Raw Dataset:** `data/raw/bank_data.csv` (`255` rows, `12` columns)[cite: 3, 19]
- **Cleaned Dataset:** `data/processed/bank_data_cleaned.csv` (`250` rows, `12` columns)[cite: 19]
- **Duplicates Removed:** `5` exact duplicate rows (`C1092`, `C1093`, `C1173`, `C1180`, `C1202`)[cite: 3].
- **Text Standardization:** Cleaned `7` inconsistent `City` entries using `.str.strip().str.title()` across `Mumbai` (`69`), `Delhi` (`66`), `Bengaluru` (`45`), `Lucknow` (`36`), and `Ghaziabad` (`34`)[cite: 3].
- **Missing Values Imputed:** Filled `NaN` values in `Employment_Type` (`5` -> mode `Salaried`), `Monthly_Income` (`5` -> median `43500.0`), `Tenure_Years` (`5` -> median `4.6`), and `Monthly_Transactions` (`6` -> median `27.0`)[cite: 3].
- **Impossible Age Fixed:** Replaced out-of-range `Age` values (`-27` in `C1150` and `212` in `C1134`) with valid median age (`37.0`)[cite: 3].

## 4. Key Analytical Findings
- **Balance by City:** Mean `Avg_Monthly_Balance` is highest in `Ghaziabad` (`₹64,785.29`, median `₹61,500`) and `Bengaluru` (`₹63,022.22`, median `₹54,000`), followed by `Lucknow` (`₹61,680.56`), `Mumbai` (`₹57,369.57`), and `Delhi` (`₹51,751.52`).
- **Balance by Account Type:** `Current` accounts record the highest mean balance (`₹70,878.79`), followed by `Salary` (`₹62,194.52`), `Joint` (`₹54,115.38`), and `Savings` (`₹53,788.98`).
- **Preferred Channel Usage:** `Mobile_App` (`115` customers, mean `28.00` monthly transactions) and `Net_Banking` (`66` customers, mean `₹64,401.52` balance) lead digital engagement, while `Branch` (`43`) and `ATM` (`26`) represent traditional usage.
- **Correlation Drivers:** `Tenure_Years` (`r = +0.58`) and `Monthly_Income` (`r = +0.49`) show positive correlation with `Avg_Monthly_Balance`, whereas `Monthly_Transactions` (`r = +0.04`) and `Age` (`r = +0.04`) are weakly correlated and `Branch_Visits` (`r = -0.11`) has a slight negative correlation.

## 5. Visualizations (`images/`)
1. `images/01_customer_distribution_by_city.png` — Customer count across cities[cite: 19].
2. `images/02_account_type_distribution.png` — Distribution of `Savings`, `Salary`, `Current`, and `Joint` accounts[cite: 19].
3. `images/03_employment_type_distribution.png` — Customer breakdown by employment status[cite: 19].
4. `images/04_preferred_banking_channel.png` — Preferred banking channel distribution (`Mobile_App`, `Net_Banking`, `Branch`, `ATM`)