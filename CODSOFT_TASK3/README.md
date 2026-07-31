# CODSOFT Task 3 - Data Visualization Dashboard

## Overview
This repository contains the project for **Task 3: Data Visualization Dashboard** as part of the **CodSoft Data Analytics Internship**.

In this task, we focus on **data visualization** and communicating key analytical insights clearly. Using Python, Pandas, Matplotlib, and Seaborn, we develop several charts to display distributions, trends, shares, and relationships. We also prepare a dataset and detailed manual builder guide for an interactive dashboard in Microsoft Power BI.

---

## Objective
The primary objectives of this project are:
1. Design meaningful visualizations showing comparative performance, chronology, composition, frequency distribution, and relational interactions.
2. Polish all charts with professional styling (titles, axis labels, legends, customized colors).
3. Extract core findings and present them through simple, understandable visual insights.
4. Export the dashboard data (`dashboard/dashboard_data.csv`) and document step-by-step layout and measure instructions for Power BI Desktop.

---

## Dataset Description
The analysis utilizes the preprocessed sales dataset located in `Data/cleaned_data.csv`.

* **Total Records:** 5,000 transactions
* **Total Features:** 12 columns
* **Dataset Domain:** Transactional retail sales records spanning from Jan 1, 2022 to Sep 9, 2035 (exactly one sale per day).
* **Important Metrics:** `revenue` (sales value), `unit_price`, `quantity`, `discount` (applied rates), `delivery_days` (operational log time), `customer_rating` (customer satisfaction).

---

## Visualizations Created
We generated the following high-resolution charts (saved as PNGs inside the `charts/` folder):
1. **Bar Chart:** Total Sales Revenue by Product Category.
   - *Visualizes comparative sales; shows Electronics and Clothing as our primary drivers.*
2. **Line Chart:** Monthly Sales Revenue Trend (2022 - 2035).
   - *Tracks sales chronologically; reveals highly stable, stationary monthly fluctuations.*
3. **Pie Chart:** Transaction Proportions by Payment Method.
   - *Shows parts-of-a-whole shares; highlights Card as the dominant checkout option.*
4. **Histogram:** Frequency Distribution of Sales Revenue.
   - *Displays value spreads; shows a right-skewed shape with median ($796.65) and mean ($1,021.96) overlays.*
5. **Scatter Plot:** Unit Price vs. Revenue.
   - *Illustrates individual relationships; highlights a strong positive correlation ($0.678$) where pricing is uniform across all category groups.*
6. **Additional Charts:**
   - **Correlation Heatmap:** Evaluation of all continuous variables.
   - **Regional Revenue Box Plot:** Evaluation of interquartile ranges and medians across East, West, North, and South.

---

## Key Visual Insights
1. **Electronics Leads Revenue:** Generated **$1,829,899.22** (35.8% of total revenue) across 1,777 transactions.
2. **Sales are balanced regionally:** West ($1.35M) leads slightly, but all regions generate above $1.2M.
3. **Card payments are standard:** Accounts for **45.4%** of all transactions, followed by COD at 35.5%.
4. **Revenue skewness:** Transaction value has a moderately right-skewed distribution centered around a median of **$796.65** and stretched by large orders up to $4,119.33.
5. **Operational Consistency:** Customer rating (~2.97) and delivery time (~6.12 days) are stable across all categories and regions.
6. **Promotions have no volume effect:** Discount rates show zero correlation ($-0.004$) with quantity ordered, proving that offering higher discounts does not increase transaction order volumes.

---

## Interactive Dashboard Preparation
The project is prepared for Microsoft Power BI Desktop. We have provided:
* **[`dashboard/dashboard_data.csv`](file:///c:/Users/DELL/Desktop/CodSoft/CODSOFT_TASK3/dashboard/dashboard_data.csv)** - Structured dataset with added calendar fields (`Year`, `Month`, `Month_Number`, `Quarter`) to serve as a clean datasource.
* **[`dashboard/POWER_BI_INSTRUCTIONS.md`](file:///c:/Users/DELL/Desktop/CodSoft/CODSOFT_TASK3/dashboard/POWER_BI_INSTRUCTIONS.md)** - Step-by-step instructions detailing exact field mappings, dashboard layout canvas, and DAX calculations.

---

## Technologies Used
* **Python 3**
* **Pandas** (Data prep)
* **NumPy** (Numerical operations)
* **Matplotlib** and **Seaborn** (Visual plotting)
* **Jupyter Notebook** (Interactive analysis environment)
* **Dashboard Target:** Microsoft Power BI Desktop

---

## Repository Structure
```text
CODSOFT_TASK3/
│
├── charts/
│   ├── bar_chart.png
│   ├── line_chart.png
│   ├── pie_chart.png
│   ├── histogram.png
│   ├── scatter_plot.png
│   ├── correlation_heatmap.png
│   └── regional_revenue_boxplot.png
│
├── Data/
│   └── cleaned_data.csv          # Cleaned dataset (input for analysis)
│
├── dashboard/
│   ├── dashboard_data.csv        # Power BI-ready dataset
│   └── POWER_BI_INSTRUCTIONS.md  # Detailed manual dashboard builder instructions
│
├── visualization.ipynb           # Notebook generating all visuals and exports
├── VISUALIZATION_REPORT.md       # Visual findings report
├── README.md                     # Project documentation
└── requirements.txt              # Project dependencies
```

---

## How to Run & Reproduce
1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
2. Run the Jupyter Notebook to regenerate all charts and datasets:
   ```bash
   jupyter notebook visualization.ipynb
   ```

---

## Output Location
* **Generated Charts:** [`charts/`](file:///c:/Users/DELL/Desktop/CodSoft/CODSOFT_TASK3/charts/)
* **Dashboard Assets:** [`dashboard/`](file:///c:/Users/DELL/Desktop/CodSoft/CODSOFT_TASK3/dashboard/)

## Internship Program
* **Organization:** CodSoft
* **Role:** Data Analytics Intern
* **Task 3:** Data Visualization Dashboard
