Dashboard Bundesliga Analytics.png
# ⚽ Football Data Engineering with PySpark & Databricks

## 📌 Project Overview

This project is an end-to-end Big Data Engineering pipeline built with **PySpark** and deployed on **Databricks** to analyze football match performance across multiple seasons.

The pipeline processes football match datasets, calculates advanced KPIs for each team, ranks teams season by season, identifies champions, and stores optimized analytical datasets in partitioned Parquet format for scalable analytics and Business Intelligence usage. 

By migrating the workflow from a local/Colab environment to an enterprise-grade **Databricks Cluster**, this project simulates a real-world, cloud-native Data Engineering workflow used in modern analytics platforms.

---

# 🎯 Objectives

- Build a scalable PySpark data pipeline.
- Deploy and execute the pipeline on a managed **Databricks Cloud Cluster**.
- Perform football analytics using distributed processing.
- Calculate advanced KPIs per team and season.
- Rank teams using Window Functions.
- Identify champions for each season.
- Store optimized datasets in Parquet format via DBFS (Databricks File System) / Local Workspace.
- Create visualizations for football performance analysis.
- Integrate processed data with Power BI.

---

# 🏗️ Architecture

```text
CSV Dataset (Uploaded to Cloud / DBFS)
    ↓
PySpark Ingestion (Databricks Cluster)
    ↓
Data Cleaning & Preparation
    ↓
Feature Engineering
    ↓
Aggregations & KPIs
    ↓
Window Functions & Ranking
    ↓
Parquet Partitioned Storage
    ↓
Power BI / Interactive BI Dashboards

```

---

# 🛠️ Technologies Used

* **Languages:** Python, SQL (DAX for Power BI)
* **Big Data Framework:** Apache Spark (PySpark), Spark DataFrame API
* **Cloud Platform:** Databricks (Workspace, Compute Clusters, DBFS)
* **Development Environment:** Google Colab, Databricks Notebooks
* **Visualization:** Pandas, Matplotlib, Seaborn, Databricks `display()` function
* **Business Intelligence:** Power BI
* **Storage:** Parquet (Columnar Storage)
* **Version Control:** Git & GitHub

---

# 📂 Project Structure

```text
football-data-engineering/
│
├── data/
│   ├── raw/
│   │   └── football_dataset.csv
│   │
│   ├── processed/
│   │   ├── football_stats_partitioned/
│   │   └── football_top_teams/
│
├── notebooks/
│   ├── football_pipeline_colab.ipynb
│   └── football_pipeline_databricks.ipynb
│
├── visualizations/
│   ├── win_percentage.png
│   ├── goals_scored.png
│   └── goal_differentials.png
│
├── docs/
│   └── football-columns-documentation.pdf
│
├── README.md
│
└── requirements.txt

```

---

# ⚙️ Pipeline Steps

## 1️⃣ Data Ingestion

* Load CSV dataset into a PySpark DataFrame.
* Inspect schema and dataset structure.
* Rename unnecessary columns.
* Handle missing values and data types.

## 2️⃣ Feature Engineering

Create indicator columns (`HomeTeamWin`, `AwayTeamWin`, `GameTie`) to simplify analytical calculations and KPI generation.

## 3️⃣ Data Filtering

Filter for Bundesliga matches (`Div = D1`) and Seasons between `2000` and `2015`.

## 4️⃣ Aggregations & Joins

* Calculate Home and Away statistics (Goals scored, conceded, wins, losses, draws) using `groupBy()` and `agg()`.
* Merge Home and Away statistics via `inner join` to create a unified analytical dataset.

## 5️⃣ KPI Calculations

Generate advanced football KPIs: `GoalsScored`, `GoalsAgainst`, `GoalDifferentials`, `WinPercentage`.

## 6️⃣ Ranking with Window Functions

Use Spark Window Functions to partition by season and rank teams based on Win Percentage and Goal Differentials to identify champions.

## 7️⃣ ☁️ Databricks Cloud Execution & Visualization

* **Cluster Management:** Provisioned a Databricks compute cluster for distributed execution.
* **Storage Navigation:** Handled cloud security policies (navigating `DBFS_DISABLED` restrictions) by mapping data to secure Workspace paths.
* **Interactive Visualization:** Leveraged Databricks' native `display()` UI for instant, code-free data profiling and dashboarding (Bar charts for Win %, Scatter plots for performance).

## 8️⃣ Parquet Export

Export datasets in optimized Parquet format, partitioned by `Season` for optimized BI querying.

---

# 📈 Power BI Dashboard

The generated Parquet datasets are integrated into Power BI to create interactive dashboards including:

* KPI Cards (Average Win Percentage, Total Goals, Max Goal Differentials).
* Team performance analysis with Season-over-Season dynamic slicers.
* Corrected DAX measures to handle percentage normalization accurately.

---

# 🚀 Big Data Concepts Covered

* Cloud Computing & Managed Clusters (Databricks)
* Distributed Data Processing & Lazy Evaluation
* Medallion Architecture Logic (Bronze, Silver, Gold layers)
* PySpark Transformations & Actions
* Window Functions & Advanced Aggregations
* Data Partitioning & Columnar Storage (Parquet)
* Cloud Security Navigation & Debugging

---

# 💡 Why Parquet?

Parquet is used because it provides:

* Faster query performance and better compression (Columnar storage).
* Reduced storage usage, saving cloud computing costs.
* Efficient analytics processing when connected to Power BI.

---

# ▶️ How to Run the Project

## 1️⃣ Databricks Environment (Recommended)

1. Import the `football_pipeline_databricks.ipynb` notebook into your Databricks Workspace.
2. Spin up a Compute Cluster.
3. Upload the raw data and adjust the `file:/Workspace/...` path in the ingestion cell.
4. Run all cells and utilize the `display()` function for visuals.

## 2️⃣ Local / Google Colab Environment

1. Install Dependencies: `pip install -r requirements.txt`
2. Open `football_pipeline_colab.ipynb`.
3. Run all cells sequentially. Outputs will be generated in `data/processed/`.

---

# 📌 Future Improvements

* Add streaming data processing (Spark Structured Streaming).
* Integrate Apache Airflow for pipeline orchestration.
* Connect Power BI directly to Databricks SQL Warehouse (DirectQuery).
* Automate data ingestion using cloud triggers (AWS S3/Azure Blob).

---

# 👨‍💻 Author

**Developed by:** Mohamed Marra (MEDINCODEX)

**Role:** Senior Data Engineer & Data Analyst

```

```
