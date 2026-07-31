# CODSOFT Task 2 - Exploratory Data Analysis (EDA)

## Overview
This repository contains the project for **Task 2: Exploratory Data Analysis (EDA)** as part of the **CodSoft Data Analytics Internship**.

In this task, we perform a detailed exploratory data analysis to inspect the cleaned retail sales dataset, describe its attributes, examine distributions, analyze correlations, identify monthly and yearly trends, and detect anomalies. We also answer several analytical questions to help drive business decisions.

---

## Objective
The goal is to conduct an in-depth data profiling and exploration process:
1. Examine features using summary and descriptive statistics.
2. Identify and analyze data distributions and skewness.
3. Track transaction patterns and sales revenue trends over time (2022 - 2035).
4. Discover relationships, correlations, and interactions between columns.
5. Detect statistical outliers and understand if they represent legitimate observations.
6. Address key business questions and translate statistical findings into actionable business insights.

---

## Dataset Description
The analysis uses the preprocessed sales dataset located in `Data/cleaned_data.csv`.

* **Total Records:** 5,000 orders
* **Total Features:** 12 columns
* **Columns Investigated:**
  * `order_id` (int64): Unique order identifier.
  * `order_date` (object/datetime): Standardized date in `YYYY-MM-DD` format.
  * `customer_id` (int64): Unique customer identifier.
  * `product_category` (object): Electronics, Clothing, Home, or Beauty.
  * `region` (object): West, North, East, or South.
  * `quantity` (int64): Units ordered (range 1–7).
  * `unit_price` (float64): Price per unit (range $15.15 – $599.96).
  * `discount` (float64): Applied discount rate (range 0% – 35%).
  * `payment_method` (object): Card, COD, or Wallet.
  * `delivery_days` (int64): Delivery duration (range 1–11 days).
  * `customer_rating` (float64): Customer feedback rating (range 1.0 – 5.0).
  * `revenue` (float64): Transaction revenue (range $11.21 – $4,119.33).

---

## Analysis Performed
The analysis is documented step-by-step in the Jupyter Notebook `exploratory_analysis.ipynb`:
1. **Descriptive Statistics:** Calculated counts, means, medians, standard deviations, and quartile ranges.
2. **Univariate Analysis:** Analyzed individual features using histograms and KDE distributions. Checked for skewness.
3. **Categorical Breakdown:** Evaluated order frequencies and percentages for categorical segments.
4. **Bivariate / Multivariate Boxplots:** Compared categorical variables against transaction revenue.
5. **Correlation Study:** Created a correlation matrix and Seaborn heatmap.
6. **Outlier Detection:** Flagged outliers using the Interquartile Range (IQR) method and analyzed their context.
7. **Trend Analysis:** Aggregated and plotted sales performance across years and months.
8. **Business Questions:** Explored 8 distinct business inquiries, generating custom visualizations and insights.

---

## Key Findings
1. **Core Revenue Drivers:** Revenue is heavily driven by `unit_price` (correlation $0.678$) and `quantity` (correlation $0.624$). Discounts have a minor negative impact (correlation $-0.139$).
2. **Electronics leads the business:** Electronics generated the highest total revenue of **$1,829,899.22** (35.8% of total revenue) across 1,777 transactions.
3. **Regionally Balanced Sales:** Sales are distributed evenly across regions, with the **West** leading slightly at **$1,345,582.16** (26.3% of revenue).
4. **Card is the preferred payment method:** Represents **45.4%** of all orders, followed by COD at 35.5% and Wallet at 19.1%.
5. **Discounts do not drive volume:** The correlation between discount offered and quantity ordered is near zero (**-0.004**), showing that higher discounts do not increase the number of items purchased per transaction.
6. **Stable Operations:** Delivery times average **6.12 days** and customer ratings average **2.97** out of 5.0, staying consistent across all categories and regions.

---

## Technologies Used
* **Python 3**
* **Pandas** (Data manipulation)
* **NumPy** (Numerical operations)
* **Matplotlib** and **Seaborn** (Data visualization)
* **Jupyter Notebook** (Analysis environment)

---

## Repository Structure
```text
CODSOFT_TASK2/
│
├── Data/
│   └── cleaned_data.csv          # Cleaned dataset (input for analysis)
│
├── exploratory_analysis.ipynb    # Main notebook detailing the EDA steps
├── EDA_REPORT.md                 # Summary report of statistical findings and insights
├── README.md                     # Project documentation
└── requirements.txt              # Project dependencies
```

---

## Business Questions Investigated
* **Q1:** What is the total sales revenue and transaction count?
* **Q2:** Which product category contributes the most to sales revenue?
* **Q3:** How does sales revenue compare across different regions?
* **Q4:** What are the preferred payment methods of customers?
* **Q5:** Does the average customer rating vary by product category?
* **Q6:** How do average delivery days differ across geographic regions?
* **Q7:** Is there a significant relationship between discount rate and quantity ordered?
* **Q8:** How does monthly sales revenue trend over time?

---

## Conclusion
The retail operations display high stability and consistency. Since promotional discounts do not influence quantity ordered, re-evaluating the discount strategy represents a key opportunity to improve profitability.
