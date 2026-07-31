# Power BI Dashboard Instructions

This document provides step-by-step instructions to construct an interactive, professional retail analytics dashboard in **Power BI Desktop** using the prepared dataset.

---

## 1. Dataset
* **Source Path:** `dashboard/dashboard_data.csv`
* **Contents:** Cleaned retail transaction records with added temporal fields (`Year`, `Month`, `Month_Number`, `Quarter`).

---

## 2. Import Data
1. Launch **Power BI Desktop**.
2. Click **Get Data** (Home Tab) -> Select **Text/CSV**.
3. Locate and select the file `dashboard/dashboard_data.csv`.
4. Review the preview and click **Transform Data** (Power Query).
5. In the Power Query editor, confirm data columns are parsed correctly.
6. Click **Close & Apply** to load the dataset.

---

## 3. Verify Data Types
In the **Data View** (or Power Query), confirm the following data types:
* `order_id` -> Whole Number (Do not summarize)
* `order_date` -> Date (Format: `yyyy-MM-dd`)
* `customer_id` -> Whole Number (Do not summarize)
* `product_category` -> Text
* `region` -> Text
* `quantity` -> Whole Number
* `unit_price` -> Decimal Number (Format as Currency: `$`)
* `discount` -> Decimal Number (Format as Percentage: `%`)
* `payment_method` -> Text
* `delivery_days` -> Whole Number
* `customer_rating` -> Decimal Number
* `revenue` -> Decimal Number (Format as Currency: `$`)
* `Year` -> Whole Number (Do not summarize)
* `Month` -> Text
* `Month_Number` -> Whole Number (Use to sort `Month` column)
* `Quarter` -> Text

*Note: Select the `Month` column, go to **Column Tools**, and click **Sort by column** -> select `Month_Number` to ensure chronological monthly sorting in visuals.*

---

## 4. DAX Measures
Create a new table `_Measures` or add these measures to the main table. Go to **Modeling** -> **New Measure** and write the following formulas:

```dax
// 1. Total Sales Revenue
Total Revenue = SUM('dashboard_data'[revenue])

// 2. Total Transactions
Transaction Count = COUNTROWS('dashboard_data')

// 3. Average Order Size (Units)
Avg Order Quantity = AVERAGE('dashboard_data'[quantity])

// 4. Average Unit Price
Avg Unit Price = AVERAGE('dashboard_data'[unit_price])

// 5. Average Customer Rating
Avg Customer Rating = AVERAGE('dashboard_data'[customer_rating])

// 6. Average Delivery Days
Avg Delivery Days = AVERAGE('dashboard_data'[delivery_days])
```

---

## 5. KPI Cards
Add **Card** visuals to the top of your canvas for high-level summaries:

* **Card 1: Total Sales**
  - **Field:** `Total Revenue` (Format: Currency, 2 decimal places, e.g., `$5.11M`)
  - **Title/Label:** "Total Revenue"
* **Card 2: Transaction Count**
  - **Field:** `Transaction Count` (Format: Decimal, Whole Number, e.g., `5,000`)
  - **Title/Label:** "Total Transactions"
* **Card 3: Average Rating**
  - **Field:** `Avg Customer Rating` (Format: Decimal, 2 decimal places, e.g., `2.97`)
  - **Title/Label:** "Avg Customer Rating"
* **Card 4: Average Delivery Time**
  - **Field:** `Avg Delivery Days` (Format: Decimal, 2 decimal places, e.g., `6.12 Days`)
  - **Title/Label:** "Avg Delivery Days"

---

## 6. Bar Chart: Category Performance
* **Visual Type:** Clustered Bar Chart (Horizontal) or Clustered Column Chart (Vertical)
* **X-Axis / Axis:** `product_category`
* **Y-Axis / Values:** `Total Revenue` (Measure)
* **Sorting:** Sort descending by `Total Revenue`
* **Title:** "Sales Revenue by Product Category"
* **Format:** Enable Data Labels, set colors to a cohesive palette (e.g. Dark Blue).

---

## 7. Line Chart: Sales Trend Over Time
* **Visual Type:** Line Chart
* **X-Axis:** `order_date` (Use date hierarchy or date value directly; alternatively `Year` and `Month` columns for drill-down)
* **Y-Axis:** `Total Revenue` (Measure)
* **Title:** "Monthly Sales Revenue Trend"
* **Format:** Enable markers, set line color to royal blue, set gridlines to dotted.

---

## 8. Pie/Donut Chart: Payment Method Proportions
* **Visual Type:** Donut Chart
* **Legend:** `payment_method`
* **Values:** `Transaction Count` (Measure)
* **Title:** "Transactions by Payment Method Share"
* **Format:** Show "Category, Percent of total" in data labels.

---

## 9. Scatter Plot: Price vs. Revenue
* **Visual Type:** Scatter Chart
* **X-Axis:** `unit_price` (Column)
* **Y-Axis:** `revenue` (Column)
* **Legend (optional):** `product_category`
* **Title:** "Unit Price vs. Revenue Transaction Level Scatter Plot"
* **Format:** Set bubble transparency to 20%, size to a readable scale.

---

## 10. Slicers / Interactive Filters
Add **Slicer** visuals to the side or top panel to enable user interaction:
* **Slicer 1 (Date Slider):** `order_date` (Set as "Between" slider range)
* **Slicer 2 (Region Dropdown):** `region` (List selection or Dropdown list)
* **Slicer 3 (Category Checkboxes):** `product_category` (Horizontal tile format or checklist)

---

## 11. Dashboard Layout Plan
A suggested layout canvas is shown below:

```text
---------------------------------------------------------------------------------
|  RETAIL PERFORMANCE ANALYTICS DASHBOARD                                        |
---------------------------------------------------------------------------------
|  [SLICERS: Region (All) | Category (All) | Date range slider                 ] |
---------------------------------------------------------------------------------
|  [KPI CARD]           [KPI CARD]            [KPI CARD]           [KPI CARD]    |
|  Total Revenue        Total Transactions    Avg Customer Rating  Avg Deliv.    |
|  $5.11M               5,000                 2.97                 6.12 Days     |
---------------------------------------------------------------------------------
|  [LINE CHART]                                        | [DONUT CHART]          |
|  Monthly Sales Revenue Trend                         | Payment Method Share   |
|  (Line showing stable stationary fluctuations)       | Card (45.4%), COD...   |
---------------------------------------------------------------------------------
|  [BAR CHART]                                         | [SCATTER CHART]        |
|  Revenue by Product Category                         | Unit Price vs Revenue  |
|  Elec ($1.83M) > Cloth ($1.53M) > Home...            | (Positive linear plot) |
---------------------------------------------------------------------------------
```

---

## 12. Visual Formatting & Theme Recommendations
* **Theme:** Use **"Executive"** or **"Classic"** built-in Power BI themes. A dark header band with light backgrounds keeps formatting corporate and readable.
* **Fonts:** Use **Segoe UI** or **Segoe UI Semibold** consistently.
* **Numbers:** Explicitly format currencies to `$#,##0.00` and counts to `#,##0`.
* **Titles:** Keep visual titles concise, centered or left-aligned, size 12-14pt bold.

---

## 13. Save Dashboard
Save your completed work in the dashboard directory as:
* **`dashboard/retail_sales_dashboard.pbix`**
