# Customer Shopping Behavior Analysis 🛒📊

An end-to-end data analysis project that uncovers insights into customer spending patterns, operational metrics, and demographic trends using Python, SQL, and Power BI.

---

## 📌 Project Overview

This project analyzes transactional data from 3,900 purchases across various product categories. The goal is to uncover actionable insights into spending patterns, customer segmentation, product preferences, and subscription behaviors to drive data-informed business decisions.

---

## 🛠️ Tech Stack & Tools

* **Data Cleaning & Engineering:** Python (Pandas)
* **Database Management & Querying:** PostgreSQL
* **Data Visualization & Reporting:** Power BI

---

## 📊 Dataset Summary

* **Dataset Size:** 3,900 rows | 18 columns
* **Demographics:** Age, Gender, Location, Subscription Status
* **Purchase Details:** Item Purchased, Category, Purchase Amount (USD), Season, Size, Color
* **Behavioral Features:** Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type
* **Data Quality Issues:** 37 missing values found and handled in the `Review Rating` column.
<img width="787" height="283" alt="image" src="https://github.com/user-attachments/assets/561cdd72-9137-4115-860e-e4555c787fe0" />

---

## 🚀 Execution Workflow

### 1. Data Cleaning & Feature Engineering (Python)
The initial preprocessing was executed in Jupyter Notebooks/Python scripts using `pandas`:
* **Data Quality:** Imputed missing `Review Rating` values using the median rating of their respective product categories.
* **Standardization:** Renamed dataset columns to clean `snake_case`.
* **Feature Engineering:**
  * Created `age_group` by binning customer ages.
  * Created `purchase_frequency_days` from transactional intervals.
* **Redundancy Control:** Checked for data redundancy between `discount_applied` and `promo_code_used`; safely dropped `promo_code_used`.
* **ETL Pipeline:** Connected Python to a local PostgreSQL instance and exported the structured DataFrame into a database table.

### 2. Structured Business Analysis (SQL)
Advanced business queries were executed in PostgreSQL to answer 10 key structural questions:
1. **Revenue by Gender:** Total spending breakdown between male and female buyers.
2. **High-Spending Discount Users:** Customers utilizing discounts who still spend above average.
3. **Top 5 Products by Rating:** Top items based on highest average review metrics.
4. **Shipping Type Comparison:** Average order value (AOV) comparison between Standard and Express shipping.
5. **Subscribers vs. Non-Subscribers:** Core operational KPIs filtered by subscription tier.
6. **Discount-Dependent Products:** Identifying top 5 items most frequently bought on discount.
7. **Customer Segmentation:** Classification of base into *New*, *Returning*, and *Loyal* user cohorts.
8. **Top 3 Products per Category:** Granular performance ranks across product categories.
9. **Repeat Buyers & Subscriptions:** Core correlation analysis on high-frequency buyers.
10. **Revenue by Age Group:** Financial performance segmented by demographic age tiers.

### 3. Interactive Reporting (Power BI)
<img width="787" height="437" alt="image" src="https://github.com/user-attachments/assets/7cc15675-d438-4adb-a8a3-24f0be21c269" />
An interactive dashboard was constructed to visually track:
* Total unique customer distributions (3.9K)
* Global Average Purchase Amount (\$59.76) & Average Review Rating (3.75)
* Category metrics, Subscription splits (27% Yes / 73% No), and Revenue breakdowns by Age Group.

---

## 🎯 Key Business Recommendations

* **Boost Subscriptions:** Launch targeted campaigns to convert the 73% non-subscribers by advertising exclusive perks.
* **Customer Loyalty Programs:** Target the "Returning" buyer pool to push them into the "Loyal" segment (currently at 3,116 customers).
* **Optimize Discount Policies:** Taper down margin-eating discounts on discount-dependent products like Hats and Sneakers.
* **Product Positioning:** Highlight top-rated item inventory (e.g., Gloves, Sandals, Boots) during core seasonal marketing.

---

## 📂 Project Structure

```text
├── data/
│   └── shopping_behavior_dataset.csv   # Raw transactional data
├── scripts/
│   ├── data_preprocessing.py            # Python cleaning & PostgreSQL upload script
│   └── business_queries.sql             # Comprehensive SQL script containing 10 business queries
├── dashboard/
│   └── customer_behavior_db.pbix        # Interactive Power BI dashboard file
└── README.md                            # Project documentation
```

---

## 💻 Getting Started

### Prerequisites
Ensure you have the following installed on your machine:
* Python 3.8+ (with `pandas` and `sqlalchemy`/`psycopg2`)
* PostgreSQL 13+
* Power BI Desktop

### Setup & Installation
1. **Clone the repository:**
   ```bash
   git clone https://github.com
   cd customer-shopping-analysis
   ```
2. **Install Python requirements:**
   ```bash
   pip install pandas sqlalchemy psycopg2
   ```
3. **Run the cleaning script:** Execute the preprocessing file to clean the data and automatically migrate it into your PostgreSQL environment.
