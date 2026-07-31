# CODSOFT Task 1 - Data Cleaning & Preprocessing

## Overview
This repository contains the project for **Task 1: Data Cleaning & Preprocessing** as part of the **CodSoft Data Analytics Internship**. 

Data cleaning is a critical first step in any data analysis workflow. This project demonstrates how to inspect, clean, validate, and preprocess a retail sales dataset using **Python** and **Pandas**.

## Objective
The primary goal of this project is to convert a raw, un-preprocessed sales dataset into a clean, verified, and standardized version ready for downstream analysis.

Specifically, the workflow demonstrates:
1. Importing the dataset using Pandas.
2. Inspecting the dataset's structural layout and statistics.
3. Identifying and handling missing values.
4. Detecting and handling duplicate records.
5. Investigating and correcting casing or whitespace inconsistencies in categorical text fields.
6. Correcting inappropriate data types (e.g., date strings to datetime objects).
7. Validating numeric fields for logical ranges and mathematical consistency.
8. Saving and exporting the finalized cleaned data.

---

## Dataset Description
The dataset used in this project is located in `Data/Raw_data_RetailSales.csv`.

* **Total Records:** 5,000
* **Total Features:** 12
* **Data Fields:**
  * `order_id` (int64): Unique transaction identifier
  * `order_date` (object/string): Transaction date (e.g., M/D/YYYY)
  * `customer_id` (int64): Unique customer identifier
  * `product_category` (object/string): Category of product (Electronics, Clothing, Home, Beauty)
  * `region` (object/string): Geographic sales region (West, North, East, South)
  * `quantity` (int64): Number of items ordered
  * `unit_price` (float64): Price per item
  * `discount` (float64): Applied discount rate (ranging from 0% to 35%)
  * `payment_method` (object/string): Payment method (Card, COD, Wallet)
  * `delivery_days` (int64): Days taken to deliver the order
  * `customer_rating` (float64): Customer feedback score (1.0 to 5.0)
  * `revenue` (float64): Calculated revenue for the transaction

---

## Data Cleaning Process
The cleaning process is documented step-by-step in the Jupyter Notebook `data_cleaning.ipynb`:
1. **Initial Inspection:** Analyzed data shapes, types, columns, and general statistical characteristics.
2. **Missing Value Audit:** Programmatically scanned all columns. Since the raw data contained no missing values, we documented this without modifying the clean state.
3. **Duplicate Audits:** Evaluated duplicate rows (including and excluding ID fields). The dataset has zero duplicate transactions.
4. **Consistency Verification:** Checked categorical columns for trailing/leading whitespaces and inconsistent casing. Checked categories were uniform and normalized.
5. **Data Type Correction:** Converted the `order_date` column to proper `datetime64[ns]` format. Upon conversion, date formats were verified to be in standard ISO-8601 `YYYY-MM-DD` style.
6. **Data Validation:** Checked numerical bounds (no negative prices or invalid ratings) and confirmed that the `revenue` field mathematically matches the formula `quantity * unit_price * (1 - discount)` within decimal rounding limits.

---

## Technologies Used
* **Python 3**
* **Pandas** (Data analysis)
* **NumPy** (Numerical operations)
* **Jupyter Notebook** (Interactive analysis environment)

---

## Repository Structure
```text
CODSOFT_TASK1/
│
├── Data/
│   ├── Raw_data_RetailSales.csv  # Original raw dataset (preserved)
│   └── cleaned_data.csv          # Cleaned, preprocessed dataset
│
├── data_cleaning.ipynb           # Jupyter Notebook detailing the data cleaning
├── README.md                     # Project documentation
└── requirements.txt              # Required python dependencies
```

---

## Cleaning & Preprocessing Results

| Metric | Before Cleaning | After Cleaning |
| :--- | :--- | :--- |
| **Total Rows** | 5,000 | 5,000 |
| **Total Columns** | 12 | 12 |
| **Missing Values** | 0 | 0 |
| **Duplicate Rows** | 0 | 0 |
| **`order_date` Data Type** | `object` (string) | `datetime64[ns]` |
| **Date Format** | `M/D/YYYY` (e.g. `1/1/2022`) | `YYYY-MM-DD` (e.g. `2022-01-01`) |

---

## Output
The final cleaned dataset is exported as:
* [cleaned_data.csv](file:///c:/Users/DELL/Desktop/CodSoft/CODSOFT_TASK1/Data/cleaned_data.csv)

All dates have been standardized, numeric fields validated, and the data format is ready for visualization, exploratory data analysis (EDA), or machine learning model training.

## Internship Program
* **Organization:** CodSoft
* **Role:** Data Analytics Intern
* **Task 1:** Data Cleaning & Preprocessing
