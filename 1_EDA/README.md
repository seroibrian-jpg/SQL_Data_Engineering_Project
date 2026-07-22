# Exploratory Data Analysis w/SQL: Job Market Analysis

 
 ![Alt Text](../images\1_1_Project1_EDA.png)

 A SQL project analyzing the data engineer job market using real woorld job posting data. It demonstrates my ability to **write production-quality analytical SQL,design effective queries and turn business questions into data driven insights**.

## Executive Summery

- ✅ **Project scope:** Built **3 analytical queries** that answer key questions about the data engineer job market  
- ✅ **Data modeling:** Used **multi-table joins** across fact and dimension tables to extract insights  
- ✅ **Analytics:** Applied **aggregations, filtering, and sorting** to find top skills by demand, salary, and overall value  

If you have a minute, revew these:

1. [Top_Demanded_Skills.sql](/1_EDA/01_top_demanded_skills.sql) - Demand analysis with multi-table joins.

2. [Top_paying_skils.sql](/1_EDA/02_top_paying_skills.sql) - Salary analysis with aggregations.

3. [Optimal_skills.sql](/1_EDA/03_optimal_skills.sql)- Combined demand/salary optimization.

## Problem & Context
Job market analysts need to answer questions like:
- ☝️ **Most in-demand:** *Which skills are the most in-demand for Data Engineers?*
- 💰 **Highest Paid:** *Which skills command the Highest salaries?*
- 🔔**Best trade-off:** *What is the optimal skill set balancing demand and compensations?*

This project analyzes a **Data Warehouse** built using star schema design. The warehouse structure consist of: 

![Data Warehouse](../images/1_2_Data_Warehouse.png)

- **Fact Table:** `job_postings-fact` - Central table containing job postings details(job titles, location, salaries, date, etc)

- **Dimension Tables:**  
    - `company_dim` - Company details linked to job postings
    - `skills_dim` - Skills catalog with skills names and types

- **Bridge Table:** `skills_jobs_dim`- REsolves the many-to-many relationship between job postings and skills 

By querrying between these interconected tables, I extracted insights about skills demand, salary patterns, and optimal skill combinations for data Engineering roles.
## Tech Stack
- 🦆**Query Engine:** DuckDB for fast OLAP-style analytical querries.  

- 🧮 **Language:** SQL (ANSI-style with analytical functions)

- 📊 **Data Model:** Star schema with fact + bridge tables

- 🛠️ **Developement:** VS Code for SQL editing + terminal for DuckDB CLI.
- 📦 **Version Control:** Git/GitHub for versioned SQL scripts.


## 🏗 Analysis Overview

### Query Structure
1. [Top Demanded Skills.sql](/1_EDA/01_top_demanded_skills.sql) - Demand analysis with multi-table joins.

2. [Top paying skils.sql](/1_EDA/02_top_paying_skills.sql) - Salary analysis with aggregations.

3. [Optimal skills.sql](/1_EDA/03_optimal_skills.sql)- Combined demand/salary optimization.

### Key Insights
- 🧠 `Core languages:` SQL and Python each appear in ~29,000 job postings, making them the most demanded skills  
- ☁️ `Cloud platforms:` AWS and Azure are critical for modern data engineering roles  
- 🧱 `Infra & tooling:` Kubernetes, Docker, and Terraform are associated with premium salaries  
- 🔥 `Big data tools:` Apache Spark shows strong demand with competitive compensation

## 💻SQL Skills Demonstrated

### Query Design & Optimization 
- ** Complex Joins:** Multi-table `INNER JOIN` operations across `job_postings_fact`, `skills_job_dim`, and `skills_dim `  

- **Aggregations:** `COUNT()`, `MEDIAN()`, `ROUND() ` for statistical analysis   

- **Filtering:** Boolean logic with `WHERE` clauses and multiple conditions (`job_title_short`, `job_work_from_home` ,`salary_year_avg IS NOT NULL`)  

- **Sorting & Limiting:** `ORDER BY` with `DESC` and `LIMIT` for top-N analysis  

### Data Analysis Techniques 

- **Grouping:** `GROUP BY` for categorical analysis by skill

- **Conditional Logic:** `CASE WHEN` statements for derived metrics

- **Mathematical Functions:** `LN()` for natural logarithm transformation to normalize demand metrics

- **Calculated Metrics:** Derived optimal score  combining long-transformed demand with median salary 
- **HAVING Clauses:** Filtering aggregated results (skills with >=100 postings)

- **NULL Handling:** Proper filtering of incoplete records (`salary_year_avg IS NOT NULL`)