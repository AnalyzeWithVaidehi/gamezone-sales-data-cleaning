# 🎮 GameZone Data Cleaning: Sourcing, Auditing, and Fixing 20k+ Raw E-Commerce Records

---

## 👋 Meet the Analyst

**Hi, I'm Vaidehi!** I am a Data Analyst specializing in bridging the gap between raw data chaos and clean, reliable business strategies. With a background in computer science and digital marketing analytics, I don't just look at data as numbers in a grid—I look at it as a map of customer behavior and operational health. 

* **🛠 My Tech Stack:**  Excel, Power BI/Tableau, SQL (Window Functions, CTEs, Complex Joins) and Python (Pandas, Numpy, Matplotlib, Seaborn).
* **🎯 My Philosophy:** A dashboard is only as good as the data feeding it. I focus heavily on data pipeline integrity, automated validation checks, and building clean data structures before driving business visualization.
* **📬 Connect with Me:** [linkedin](https://www.linkedin.com/in/vaidehibharambeaulagar)  | vaidehibh@gmail.com

---

## 📌 Project Overview: Why this project?
GameZone is a global e-commerce platform that has been selling gaming hardware since 2018. They have amassed over 20,000 transaction records, but the data was too unrefined to trust for regional reporting. If leadership built dashboards using this raw data, their revenue figures, product metrics, and regional strategies would be completely skewed.

**My Mission:** Step in as the primary data engineer/analyst to audit, clean, and format this massive data dump. I transformed a chaotic, bug-ridden spreadsheet into a trusted, fully documented data foundation that the business team can immediately use for strategic reporting.


## 🔍 The Audit Trail: Key Issues Found & Solved
Data cleaning is an iterative process. I tracked every single step, row count, and proportional impact inside my [Comprehensive Issue Log](./gamezone_issue_log.csv). Here are the primary issues I intercepted:

1.  **Inconsistent Product Categorization:** Variations like `"27inches 4k gaming monitor"` vs `"27in 4K gaming monitor"` were artificially splitting performance tracking. I standardized these into clean, distinct product categories.
2.  **The "Time Travel" Logistics Bug:** Found critical system errors where `SHIP_TS` (ship date) occurred *before* the `PURCHASE_TS` (purchase date)—e.g., purchased Dec 24th, shipped Dec 13th. I flagged these logical errors for data integrity.
3.  **Missing Operational Metadata:** 83 entries lacked both marketing attribution and account creation parameters. Rather than dropping the data and losing valuable revenue tracking, I re-assigned them systematically to `"unknown"`.
4.  **Zero-Dollar Transacting & Duplicate Orders:** Discovered exact structural duplicate rows and several $0 transactions. I isolated these specifically to review with engineering and stakeholder channels rather than guessing the true intent.

---

## 🚀 Future-Proofing: How I Would Scale This in Production
Manual auditing doesn't scale when an e-commerce platform jumps from 20,000 rows to 20 million rows. If I were managing this pipeline on the job, I would introduce two key structural changes:

* **Front-End System Validation:** The shipping date bug is a software interface glitch. I would collaborate with the engineering team to deploy mandatory input constraints on the website/app backend so a fulfillment event can never physically log a timestamp prior to order creation.
* **Automated Data Quality Tests:** I would replace manual validation sheets with automated quality assurance checks (using tools like `dbt` or scheduled Python workflows) to automatically quarantine conflicting rows or null values the moment they arrive in the data warehouse.

---

## 📂 What’s Inside This Repository?
* `/data/gamezone-orders-data.xlsx`: The unedited, raw messy transaction records.
* `/data/gamezone_orders-data_cleaned`: The ready-for-dashboard production tables.
* `My Thought Process.pdf`: File that contains what was I thinking during my analysis, 
* `gamezone_issue_log.csv`: My step-by-step audit trail logging data magnitude, solvability, and final technical resolutions.
* `gamezone_Pivot_for_order_duplicates.csv`: Focused isolating matrix to flag duplicate order spikes.

---
*💡 What's next? Now that the data pipeline is entirely reliable, my next sprint is launching the Exploratory Data Analysis (EDA) and designing interactive regional sales dashboards in Power BI!*

