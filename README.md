# 🛍️ Customer Shopping Behavior Analysis

An end-to-end data analytics project examining **3,900 customer transactions** across various product categories. This project covers the complete data lifecycle—Exploratory Data Analysis (EDA) in **JupyterLab** using **Python**, structured querying in **MySQL Database**, interactive dashboarding in **Power BI**, and strategic business recommendations.

---

## 📌 Table of Contents
- [Project Overview](#-project-overview)
- [Tech Stack](#-tech-stack)
- [Dataset Summary](#-dataset-summary)
- [Data Pipeline & Methodology](#-data-pipeline--methodology)
  - [1. Data Preprocessing & EDA (JupyterLab + Python)](#1-data-preprocessing--eda-jupyterlab--python)
  - [2. Database Integration & SQL Analysis (MySQL)](#2-database-integration--sql-analysis-mysql)
  - [3. Interactive Visualization (Power BI)](#3-interactive-visualization-power-bi)
- [Key Business Insights](#-key-business-insights)
- [Power BI Dashboard Overview](#-power-bi-dashboard-overview)
- [Strategic Business Recommendations](#-strategic-business-recommendations)
- [How to Run This Project](#-how-to-run-this-project)

---

## 🎯 Project Overview

Understanding customer purchasing patterns, subscription habits, discount sensitivities, and demographic preferences is vital for retail strategy.

**Goals of this project:**
- Perform Exploratory Data Analysis (EDA) in **JupyterLab** to clean and transform 3,900 transactional records.
- Impute missing values and engineer new features (`age_group`, `purchase_frequency_days`).
- Export processed data into **MySQL Database** for business transaction analysis using SQL queries.
- Build an interactive **Power BI Dashboard** for executive reporting and dynamic filtering.
- Formulate data-driven business recommendations to boost customer retention and average spend.

---

## 🛠️ Tech Stack

- **Environment & IDE:** JupyterLab
- **Data Analysis & Processing:** Python (`pandas`, `numpy`)
- **Database & Querying:** MySQL Database (SQL queries, aggregations, window functions)
- **Database Connector:** `SQLAlchemy` / `PyMySQL` / `mysql-connector-python`
- **Data Visualization & Dashboards:** Power BI Desktop

---

## 📊 Dataset Summary

- **Total Records:** 3,900 transactions
- **Total Attributes:** 18 columns
- **Key Features:**
  - **Demographics:** `Age`, `Gender`, `Location`, `Subscription Status`
  - **Purchase Details:** `Item Purchased`, `Category`, `Purchase Amount (USD)`, `Season`, `Size`, `Color`
  - **Shopping Dynamics:** `Discount Applied`, `Promo Code Used`, `Previous Purchases`, `Frequency of Purchases`, `Review Rating`, `Shipping Type`
- **Data Cleaning Handling:** Imputed 37 missing values in `Review Rating` using product category medians.

---

## ⚙️ Data Pipeline & Methodology

┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐ │ Raw CSV Data │ ───► │ JupyterLab │ ───► │ MySQL Database │ ───► │ Power BI │ │ (3.9k rows) │ │ (Python / EDA) │ │ (SQL Analytics) │ │ Dashboard & KPIs│ └─────────────────┘ └─────────────────┘ └─────────────────┘ └─────────────────┘



### 1. Data Preprocessing & EDA (JupyterLab + Python)
- **Exploration in JupyterLab:** Executed `df.info()` to inspect schemas and data types, and `df.describe()` for numerical distributions.
- **Missing Value Handling:** Filled 37 null values in `Review Rating` with category-wise median values.
- **Column Standardization:** Converted column titles into clean `snake_case` naming conventions.
- **Feature Engineering:**
  - Binned `Age` into categorical `age_group` (Young Adult, Middle-aged, Adult, Senior).
  - Calculated `purchase_frequency_days`.
- **Redundancy Removal:** Evaluated `discount_applied` vs `promo_code_used` and dropped redundant column `promo_code_used`.

### 2. Database Integration & SQL Analysis (MySQL)
- Connected **JupyterLab** to **MySQL** via `SQLAlchemy` & `pymysql`.
- Loaded the cleaned Pandas DataFrame directly into MySQL tables.
- Executed business queries in MySQL:
  - Total Revenue by Gender & Age Group.
  - Identification of high-spending discount users.
  - Window functions (`RANK()`) for top 3 products per category.
  - Subscriber vs Non-Subscriber spending comparisons.
  - Customer segmentation grouping (`New`, `Returning`, `Loyal`).

### 3. Interactive Visualization (Power BI)
- Connected Power BI to MySQL / processed dataset.
- Designed visual metrics including KPI cards, category breakdown bar charts, donut charts for subscription splits, and interactive slicers.

---

## 📈 Key Business Insights

### 1. Revenue & Demographic Breakdown
- **Gender Contribution:**
  - **Male:** \$157,890 (67.7% of revenue)
  - **Female:** \$75,191 (32.3% of revenue)
- **Revenue by Age Group:**
  - **Young Adult:** \$62,143 (Top revenue contributor)
  - **Middle-aged:** \$59,197
  - **Adult:** \$55,978
  - **Senior:** \$55,763

### 2. Subscription Status Analysis
- **Non-Subscribers:** 2,847 customers (73%) | Total Revenue: **\$170,436.00** | Avg Spend: **\$59.87**
- **Subscribers:** 1,053 customers (27%) | Total Revenue: **\$62,645.00** | Avg Spend: **\$59.49**
- *Key Finding:* Per-transaction spend is equal across both groups (~$59.50–$59.80), indicating high potential to convert non-subscribers without sacrificing order value.

### 3. Top Products & Discount Dependency
- **Top 5 Rated Products:** Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80), Skirt (3.78)
- **Top Discount-Dependent Items:**
  1. **Hat:** 50.00% purchases discounted
  2. **Sneakers:** 49.66% purchases discounted
  3. **Coat:** 49.07% purchases discounted
  4. **Sweater:** 48.17% purchases discounted
  5. **Pants:** 47.37% purchases discounted

### 4. Customer Segmentation
- **Loyal (>5 purchases):** 3,116 customers
- **Returning:** 701 customers
- **New:** 83 customers

---

## 🖥️ Power BI Dashboard Overview

The **Customer Behavior Dashboard** provides an executive-level interactive summary:

- **Core KPI Cards:**
  - **Total Customers:** 3.9K
  - **Average Purchase Amount:** \$59.76
  - **Average Review Rating:** 3.75
- **Visual Features:**
  - Donut Chart: `% of Customers by Subscription Status` (73% No vs 27% Yes)
  - Column / Bar Charts: `Revenue by Category` & `Sales by Category` (Clothing leading, followed by Accessories, Footwear, Outerwear)
  - Horizontal Bar Charts: `Sales by Age Group` & `Revenue by Age Group`
- **Dynamic Slicers:** Filter dataset by Subscription Status, Gender, Category, and Shipping Type.

---

## 💡 Strategic Business Recommendations

1. 🚀 **Boost Subscription Conversion:**
   - Implement targeted loyalty perks or free shipping offers to convert the 73% non-subscriber majority into subscription members.
2. 🏆 **Nurture Customer Loyalty:**
   - Launch retargeting initiatives to transition the 701 "Returning" buyers into the "Loyal" segment.
3. 🏷️ **Optimize Discounting Strategy:**
   - Items like Hats and Sneakers have ~50% discount rates. Scale back discounts on high-demand categories to protect gross margins.
4. ⭐ **Highlight Top-Rated Products:**
   - Feature top-rated items (Gloves, Sandals, Boots) prominently in promotional banners and marketing campaigns.
5. 🎯 **Demographic Targeting:**
   - Focus digital ad spend on **Young Adult** and **Middle-aged** segments who generate the highest overall revenue share.

---

## 📂 Repository Structure

 ├── data/ │ ├── raw_shopping_data.csv # Raw dataset (3,900 records) │ └── cleaned_shopping_data.csv # Exported cleaned dataset ├── notebooks/ │ └── customer_behavior_eda.ipynb # JupyterLab Notebook (Pandas EDA & MySQL export) ├── sql/ │ └── mysql_customer_analysis.sql # MySQL analytical queries ├── dashboard/ │ └── customer_behavior_dashboard.pbix # Power BI dashboard file ├── README.md # Project documentation └── requirements.txt # Python dependencies



---

## 🚀 How to Run This Project

### 1. Prerequisites
- **JupyterLab** (`pip install jupyterlab`)
- **MySQL Server** & MySQL Workbench
- **Power BI Desktop**

### 2. Python Environment Setup
```bash
# Clone the repository
git clone https://github.com/your-username/customer-shopping-behavior-analysis.git
cd customer-shopping-behavior-analysis

# Install required Python packages
pip install pandas numpy sqlalchemy pymysql mysql-connector-python jupyterlab
