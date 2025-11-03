## 🧠 AI Job Market Analysis

A complete end-to-end data analytics project analyzing global AI job trends, salary insights, and skill demand using Python, SQL, Power BI, and Excel.
This project combines data cleaning, database management, visualization, and predictive analytics — giving a full picture of the AI job market landscape.

## 🎯 Project Overview

The AI Job Market Analysis project explores how salaries, job titles, and skills vary across industries and countries within the AI domain.
It includes data cleaning, database design, visualization, and trend analysis to uncover valuable hiring and salary patterns.

## 🚀 Objective

To analyze and visualize the AI job market by identifying:

Top-paying job roles in AI

Salary trends across countries

Correlation between job titles and salary levels

Insights into in-demand AI skills and tools

 🛠️ Tools & Technologies

**Data & Cleaning**
- Excel / Google Sheets — manual fixes, header standardization, quick transformations  
- Python (pandas, numpy, openpyxl) — automated cleaning and CSV export

**Storage & Database**
- SQLite — schema design, ER diagrams, joins, queries  
- SQL — data validation, aggregation and preparation for BI

**Analysis & Modeling**
- Python (matplotlib, seaborn) — exploratory data analysis, charts  
- scikit-learn — baseline linear regression model (RMSE, R²)

**Visualization & Reporting**
- Power BI — interactive dashboards, KPI cards, maps and slicers  
- PDF/PNG exports — high-quality screenshots for portfolio

**Collaboration & Delivery**
- Git / GitHub — version control and repo hosting  
- Google Colab — reproducible notebook execution (optional/cloud)

---

## 🧩 Methodology (Day-by-day summary)

**Day 1 — Data collection & initial audit**
- Collected two raw files: `ai_job_dataset` (job/skill text) and `jobdatasetproseed` (market & salary data).  
- Performed schema inspection, identified missing values, and documented problematic columns (commas in text, inconsistent headers).

**Day 2 — Cleaning & standardization**
- Standardized column headers (snake_case), removed exact duplicates, and fixed CSV quoting issues for comma-containing text.  
- Exported cleaned CSVs: `ai_job_dataset.csv` and `jobs_market.csv`.

**Day 3 — Database design & joining**
- Imported cleaned CSVs into **SQLite**, designed ER diagrams and primary/foreign keys.  
- Wrote and tested SQL joins to create the consolidated table `job_analysis`. Exported final CSV for analytics.

**Day 4 — Power BI dashboard development**
- Built a 4-page Power BI report (Overview, Salary & Experience, Salary & Job Titles, Detailed Table).  
- Implemented KPIs, map visualizations, Top-N charts, slicers, and responsive formatting; exported PBIX and report PDF/screenshots.

**Day 5 — Exploratory analysis in Python**
- Ran EDA: distributions, top skills extraction, remote-bucket analysis, and correlations between salary and features.  
- Saved plots and CSV summaries for inclusion in the report.

**Day 6 — Baseline modeling & validation**
- Created feature set (remote_ratio buckets, skill counts, categorical encodings), trained a baseline linear regression.  
- Evaluated model (RMSE, R²), saved sample predictions and discussion notes for model limitations and next steps.

---


Due to GitHub’s 25 MB file size limit, the original SQLite database is not included directly in this repository.
However, you can easily recreate the same database using the two cleaned CSV files or by extracting job_analysis.zip.

Steps to Rebuild the Database
import sqlite3
import pandas as pd

# Load CSV files
df1 = pd.read_csv('ai_job_dataset.csv')
df2 = pd.read_csv('jobs_market.csv')

# Create SQLite connection
conn = sqlite3.connect('ai_job_database.db')

# Save as database tables
df1.to_sql('ai_job_dataset', conn, index=False, if_exists='replace')
df2.to_sql('jobs_market', conn, index=False, if_exists='replace')

# Example: joining both tables
query = """
CREATE TABLE job_analysis AS
SELECT *
FROM ai_job_dataset a
JOIN jobs_market b
ON a.job_id = b.job_id;
"""
conn.execute(query)
conn.close()


Once executed, you’ll get a database identical to the one used in Power BI and Python.

## 📈 Key Insights

- **Top-paying roles** are concentrated in *Machine Learning*, *Data Science*, and *AI Engineering*.  
- **Salary** shows strong correlation with both *job title* and *company location*.  
- **Interactive dashboards** in Power BI reveal *global salary variations* and *emerging AI job trends*.  
- **Linear Regression modeling** confirms measurable relationships between *experience level*, *remote ratio*, and *compensation*.  
- The project demonstrates a full data pipeline — from raw data cleaning to predictive modeling and visualization.

---

## 🧰 How to Run

1. **Clone this repository:**
   ```bash
   git clone https://github.com/<your-username>/AI_Job_Market_Analysis.git
   Install required Python libraries:

pip install pandas numpy matplotlib seaborn scikit-learn


## Open the notebook:

Launch AI_Job_Market_Analysis.ipynb in Google Colab (recommended) or Jupyter Notebook.

## View dashboards:

Open AI_Job_Market.pbix in Power BI Desktop to explore interactive visuals.

(Optional) If you want to rebuild the SQLite database:

Extract both CSVs from data/cleaned/

Import into SQLite and recreate job_analysis using the join query provided in the SQL folder.


## 🧾 License

This project is licensed under the MIT License — feel free to use and modify it for educational or personal purposes.

## 👨‍💻 Author

Sidhant Kumar

Data Analytics | Machine Learning | Power BI Enthusiast

[GitHub](https://github.com/sidhantmkumar) | [LinkedIn](https://in.linkedin.com/in/sidhant-k-1315ba289)

## ✅ Short Summary:
A complete AI Job Market Analysis project covering end-to-end data workflows — from cleaning and SQL integration to Power BI dashboards and Python-based analysis.
