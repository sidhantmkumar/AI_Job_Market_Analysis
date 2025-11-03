🧠 AI Job Market Analysis

A complete end-to-end data analytics project analyzing global AI job trends, salary insights, and skill demand using Python, SQL, Power BI, and Excel.
This project combines data cleaning, database management, visualization, and predictive analytics — giving a full picture of the AI job market landscape.

🎯 Project Overview

The AI Job Market Analysis project explores how salaries, job titles, and skills vary across industries and countries within the AI domain.
It includes data cleaning, database design, visualization, and trend analysis to uncover valuable hiring and salary patterns.

🚀 Objective

To analyze and visualize the AI job market by identifying:

Top-paying job roles in AI

Salary trends across countries

Correlation between job titles and salary levels

Insights into in-demand AI skills and tools

🛠️ Tools & Technologies
Category	Tools Used
Data Cleaning & Preprocessing	Microsoft Excel, Python (Pandas, NumPy)
Database Management	SQLite, SQL Queries
Visualization & Reporting	Power BI
Analytics & Modeling	Python (Matplotlib, Seaborn, Scikit-learn - Linear Regression)
🧩 Methodology
Day 1 – Data Collection

Collected two raw Excel files: ai_job_dataset.xlsx and jobdatasetproseed.xlsx.

Contained job titles, locations, company details, and salary information.

Day 2 – Data Cleaning

Cleaned both Excel sheets by removing duplicates, nulls, and inconsistent text.

Standardized columns and exported as CSV files:

ai_job_dataset.csv

jobs_market.csv

Day 3 – SQL Database Integration

Imported both CSVs into SQLite.

Designed ER Diagrams for better understanding of relationships.

Used SQL joins and queries to merge datasets and create a new combined table job_analysis.

Exported the final merged data as job_analysis.csv.

Day 4 – Power BI Visualization

Built a 4-page interactive Power BI Dashboard:

Overview: Snapshot of AI job market metrics and KPIs.

Salary & Experience: Salary distribution by role and seniority.

Job Titles: Top-paying and most in-demand AI roles.

Detailed Table: Filterable, detailed data view for deeper insights.
Exported as .pbix, .pdf, and .pbit (template) files.

Day 5 & 6 – Python Analysis & Predictive Modeling

Performed advanced EDA (Exploratory Data Analysis) using Pandas & Seaborn.

Built visualizations: histograms, bar plots, box plots to analyze salary trends.

Implemented Linear Regression to find correlation between salary and other numerical attributes.
Database & Data Handling Notes

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

📈 Key Insights

Top-paying AI roles are concentrated in Machine Learning and Data Science.

Salaries show strong correlation with job title and country.

Visualization dashboards highlight global salary differences and emerging AI job trends.

Linear regression indicates measurable relationships between job-related factors and pay.
Calculated RMSE and R² for model performance evaluation.

Notebook saved as .ipynb with supporting CSV and screenshots.
🧰 How to Run

Clone this repository:

git clone https://github.com/<your-username>/AI_Job_Market_Analysis.git


Install required Python libraries:

pip install pandas numpy matplotlib seaborn scikit-learn


Open the .ipynb notebook in Google Colab or Jupyter Notebook.

For dashboard viewing, open the .pbix file in Microsoft Power BI Desktop.

🧾 License

This project is licensed under the MIT License — feel free to use and modify it for educational or personal purposes.

👨‍💻 Author

Sidhant Kumar
Data Analytics | Machine Learning | Power BI Enthusiast
[GitHub](https://github.com/sidhantmkumar) | [LinkedIn](https://in.linkedin.com/in/sidhant-k-1315ba289)

✅ Short Summary:
A complete AI Job Market Analysis project covering end-to-end data workflows — from cleaning and SQL integration to Power BI dashboards and Python-based analysis.
