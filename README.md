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
