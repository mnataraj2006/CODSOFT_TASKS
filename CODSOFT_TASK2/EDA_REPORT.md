# Exploratory Data Analysis Report

## 1. Dataset Overview
This report documents the Exploratory Data Analysis (EDA) performed on the cleaned retail sales dataset (`cleaned_data.csv`).
* **Dimensions:** 5,000 observations (rows) and 12 features (columns).
* **Key Entities:** Orders (`order_id`), Customers (`customer_id`), Product Categories (`product_category`), and Geographical Regions (`region`).
* **Analytical Objective:** Uncover individual metric distributions, analyze correlations, identify trends over time, detect anomalies/outliers, and answer key business questions to extract actionable insights.

---

## 2. Descriptive Statistics Summary
A summary of key metrics in the dataset is detailed below:
* **Transactions:** 5,000 total recorded sales.
* **Quantity Sold:** Ranged from 1 to 7 items per order, with an average of **4.04** and median of **4.00**.
* **Unit Prices:** Ranged from $15.15 to $599.96, with an average price of **$308.42** and median of **$309.89**.
* **Discounts:** Ranged from 0.00 (0%) to 0.35 (35%), averaging **0.18** (18%).
* **Delivery Days:** Ranged from 1 to 11 days, averaging **6.12** days.
* **Customer Ratings:** Ranged from 1.0 to 5.0, averaging **2.97**.
* **Revenue:** Ranged from $11.21 to $4,119.33, with an average transaction value of **$1,021.96** and median of **$796.65**.

---

## 3. Trends and Distributions
* **Metric Distributions:** 
  - `quantity`, `unit_price`, `discount`, `delivery_days`, and `customer_rating` are uniformly and symmetrically distributed, showing skewness values very close to zero ($< |0.07|$).
  - `revenue` is moderately right-skewed with a skewness of **1.00**, indicating a concentration of lower-to-middle value orders with a long tail of higher-value sales.
* **Sales Trends:**
  - Sales revenue is highly stable over time, fluctuating between **$20,000 and $45,000** monthly.
  - Overall annual sales remain constant at around **$350,000 to $400,000** between 2022 and 2035 (Note: 2035 contains partial data up to September 9th).
  - Demand is stationary, indicating a stable sales cycle with no long-term decline or expansion.

---

## 4. Relationships and Correlations
* **Primary Revenue Drivers:** Pearson correlation analysis shows a strong positive correlation between `revenue` and `unit_price` (**0.678**) and between `revenue` and `quantity` (**0.624**). Revenue is determined directly by order size and price point.
* **Discounts Impact:** There is a minor negative correlation between `revenue` and `discount` (**-0.139**) because discounts directly subtract from the subtotal.
* **Non-Linear / Negligible Relationships:** 
  - The correlation between `discount` and `quantity` is extremely close to zero (**-0.004**), indicating that discounts do not incentivize customers to order a larger number of items.
  - Customer ratings, delivery days, and other variables show near-zero correlation ($< 0.02$) with all other fields, indicating that operational performance (delivery times) does not dictate price or quantity choice.

---

## 5. Outliers and Unusual Patterns
* **Anomalies / Outliers:**
  - Outliers were audited using the standard Interquartile Range (IQR) method. No outliers were found in `quantity`, `unit_price`, `discount`, `delivery_days`, or `customer_rating`.
  - **67 outliers** were identified in `revenue` (representing 1.34% of transactions) where revenue exceeded **$3,257.43**.
  - **Interpretation:** These represent legitimate high-value transactions (orders combining maximum quantities and maximum unit prices) and represent valid data points, not errors. They were preserved to maintain analysis integrity.
* **Unusual Patterns:** No other unusual clusters, spikes, or patterns were found.

---

## 6. Business Insights
We addressed several business questions during our analysis:
* **Q1: Total Sales and Transaction count?** Total revenue generated is **$5,109,775.74** across **5,000 transactions**.
* **Q2: Which product category performs best?** **Electronics** leads with **$1,829,899.22** (35.8% of total revenue) across 1,777 transactions, followed by Clothing ($1.53M), Home ($982K), and Beauty ($765K).
* **Q3: How do sales compare across regions?** The **West** region leads with **$1,345,582.16** (26.3% of revenue), followed by North ($1.28M), South ($1.25M), and East ($1.24M). Regional sales performance is evenly distributed.
* **Q4: What are the preferred payment methods?** **Card** is the top preferred payment method at **45.4%** of orders, with Cash on Delivery (COD) representing 35.5% and digital Wallets representing 19.1%.
* **Q5: Does customer rating vary by category?** Customer ratings are highly consistent, hovering around **2.97** (Home has 2.94, Beauty has 3.01), showing similar satisfaction levels across categories.
* **Q6: Do delivery times differ by region?** Average delivery days are uniform, ranging from **6.08 days** (West) to **6.17 days** (South). There are no geographical bottlenecks.
* **Q7: Do discounts affect quantity ordered?** No, the average quantity remains stable around 4.0 items regardless of the discount rate (0% to 35%).
* **Q8: How does monthly sales revenue trend?** Monthly revenue exhibits stable fluctuations between $20k and $45k, indicating steady demand without strong seasonality.

---

## 7. Key Findings
1. **Electronics is the core category:** Generated $1.83M (35.8% of revenue) and accounted for 35.5% of total orders.
2. **Sales are balanced regionally:** West ($1.35M) leads slightly, but all regions generate above $1.2M.
3. **Card payments are standard:** Accounts for 45.4% of all transactions, showing strong cashless integration.
4. **Revenue outliers represent high-value orders:** 67 orders exceed $3,257.43, with the maximum transaction valued at $4,119.33.
5. **Promotional pricing (discounts) does not increase order sizes:** Discount rates have a correlation of -0.004 with quantity, meaning discounts do not drive volume.

---

## 8. Conclusion
The retail operations analyzed in this dataset display a highly stable, uniform, and predictable business model. Revenue is driven primarily by product price points and quantities ordered. Customer ratings (~2.97) and logistics delivery times (~6.12 days) are stable across all segments. Because promotional discounts do not influence quantity ordered, the business might optimize its margin by re-evaluating high discount rates.
