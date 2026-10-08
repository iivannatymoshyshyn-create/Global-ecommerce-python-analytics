# 📊 Global E-Commerce Data Analytics & Business Insights (Python)

An end-to-end Python data analytics project focused on exploratory data analysis (EDA), multi-table relational data cleaning, supply chain shipping efficiency, multi-region financial metrics, and weekly sales seasonality.

🔗 **[Open Google Colab Notebook](https://colab.research.google.com/drive/1F5paH1BeFk3fTY-UPezViimnh5HJHPWy?usp=sharing)**

---

## 📌 Business Case Overview
The objective of this project is to analyze a global e-commerce company's multi-year sales data operating across both online and physical store channels. The goal is to clean missing/inconsistent data, merge relational schemas, evaluate top product line margins, uncover geographic bottlenecks, and detect day-of-week sales seasonality.

The dataset consists of three relational tables:
1. `events.csv`: Order transactions, units sold, unit prices, unit costs, and dates.
2. `products.csv`: Item categories (`item_type`) and category IDs.
3. `countries.csv`: Country names, sub-regions, regions, and ISO codes.

---

## 🔑 Key Findings & Business Insights

### 💰 1. Financial Performance & Key KPIs
* **Order Scale:** Processed **1,248 orders** across **45 countries**.
* **Total Profit:** **$473.7M** with an overall **Profit Margin of 29.63%**.
* **Category Efficiency:**
  * **Top Revenue Leader:** `Office Supplies` generated the highest revenue, but ranked 2nd in net profit due to high inventory/unit costs.
  * **Highest Margin Leader:** `Cosmetics` ranked 3rd in revenue but 1st in total net profit, proving to be the most lucrative category.
  * **Low-Margin / High-Volume Magnet:** `Beverages` leads in overall order volume but ranks near the bottom in revenue and profit, serving as a "lead magnet".

### 🌍 2. Regional & Geographic Distribution
* **Market Concentration:** `Europe` is the core profit driver, accounting for **94.2% of Revenue** and **94.7% of Profit**.
* **Underdeveloped Expansion:** `Asia` represents only **5.8% of revenue** and **6.6% of orders** (82 orders vs. 1,166 in Europe), highlighting a key opportunity for strategic market expansion.

### 🚚 3. Supply Chain & Shipping Lead Times
* **Average Delivery Duration:** **25 days** average lead time (ranging from 0 to 50 days).
* **Category Lead Times:** `Personal Care` is the fastest shipping category (~20 days), whereas `Office Supplies`, `Cereal`, and `Baby Food` experience longer shipment periods (27–28 days).
* **Country Bottlenecks:** Hungary recorded the longest average lead time (>30 days), while Bulgaria and Monaco performed fastest (~26 days).

### 🗓️ 4. Day-of-Week Sales Seasonality
* **Peak Days:** Friday and Sunday exhibit the highest overall order volumes.
* **Category Spikes:**
  * **Cosmetics:** Peak sales volume occurs on **Friday** (132,147 units sold).
  * **Fruits:** Strongest demand spike on **Sunday** (128,962 units sold), reflecting weekend grocery planning.
  * **Baby Food:** Consistently stable demand throughout the entire week due to non-discretionary necessity.

---

## 🛠️ Data Cleaning & Pipeline Steps

1. **Missing Value Handling:**
   * Replaced missing `Country Code` with `"Unknown"` to retain order volume integrity.
   * Dropped rows missing `Units Sold` (~0.15% of records) and incomplete region metadata.
2. **Type Conversions & Normalization:**
   * Converted `Order Date` and `Ship Date` to `datetime64`.
   * Standardized string columns (`str.strip()`) to eliminate trailing whitespace duplicates.
3. **Feature Engineering:**
   * Calculated `Revenue`, `Total Cost`, `Profit`, and `Delivery days` (`Ship Date - Order Date`).
   * Extracted day names (`dt.day_name()`) for heatmap pivot calculations.

---

## 🧰 Tech Stack & Python Libraries
* **Python 3.x**
* **Data Processing:** `pandas`, `numpy`, `zipfile`
* **Data Visualization:** `matplotlib`, `seaborn` (Custom Heatmaps, Pie/Donut Charts, Bar Plots)
* **Environment:** Google Colab
