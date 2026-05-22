````markdown
# ⚽ Football Data Engineering with PySpark

## 📌 Project Overview

This project is an end-to-end Big Data Engineering pipeline built with PySpark to analyze football match performance across multiple seasons.

The pipeline processes football match datasets, calculates advanced KPIs for each team, ranks teams season by season, identifies champions, and stores optimized analytical datasets in partitioned Parquet format for scalable analytics and Business Intelligence usage.

The project simulates a real-world Data Engineering workflow used in modern analytics platforms.

---

# 🎯 Objectives

- Build a scalable PySpark data pipeline
- Perform football analytics using distributed processing
- Calculate advanced KPIs per team and season
- Rank teams using Window Functions
- Identify champions for each season
- Store optimized datasets in Parquet format
- Create visualizations for football performance analysis
- Integrate processed data with Power BI

---

# 🏗️ Architecture

```text
CSV Dataset
    ↓
PySpark Ingestion
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
Power BI / Visualization
````

---

# 🛠️ Technologies Used

* Python
* PySpark
* Spark DataFrame API
* Google Colab
* Pandas
* Matplotlib
* Seaborn
* Power BI
* Parquet
* GitHub

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
│   └── football_pipeline.ipynb
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

* Load CSV dataset into a PySpark DataFrame
* Inspect schema and dataset structure
* Rename unnecessary columns
* Handle missing values and data types

---

## 2️⃣ Feature Engineering

Create indicator columns:

* `HomeTeamWin`
* `AwayTeamWin`
* `GameTie`

These columns simplify analytical calculations and KPI generation.

---

## 3️⃣ Data Filtering

Filter:

* Bundesliga matches (`Div = D1`)
* Seasons between `2000` and `2015`

---

## 4️⃣ Aggregations

Calculate:

* Home statistics
* Away statistics
* Goals scored
* Goals conceded
* Wins / Losses / Draws

Using:

* `groupBy()`
* `agg()`

---

## 5️⃣ DataFrame Joins

Merge:

* Home statistics
* Away statistics

To create a unified analytical dataset.

---

## 6️⃣ KPI Calculations

Generate advanced football KPIs:

* `GoalsScored`
* `GoalsAgainst`
* `GoalDifferentials`
* `WinPercentage`
* `GoalsPerGame`
* `GoalsAgainstPerGame`

---

## 7️⃣ Ranking with Window Functions

Use Spark Window Functions to:

* Partition by season
* Rank teams
* Identify champions

Main ranking criteria:

1. Win Percentage
2. Goal Differential

---

## 8️⃣ Parquet Export

Export datasets in optimized Parquet format:

### All Teams Dataset

```text
football_stats_partitioned/
```

Partitioned by:

* Season

### Champions Dataset

```text
football_top_teams/
```

---

# 📊 Visualizations

The project includes visual analytics for:

* Champions Win Percentage
* Goals Scored
* Goal Differentials by Season

Libraries used:

* Matplotlib
* Seaborn

---

# 📈 Power BI Dashboard

The generated Parquet datasets are integrated into Power BI to create interactive dashboards including:

* Team performance analysis
* Goals statistics
* Seasonal rankings
* Dynamic filters by season and team

---

# 🚀 Big Data Concepts Covered

This project demonstrates several real-world Data Engineering concepts:

* Distributed Data Processing
* PySpark Transformations & Actions
* Window Functions
* Analytical Pipelines
* Data Lake Storage
* Partitioned Datasets
* KPI Engineering
* Big Data Optimization
* Lazy Evaluation
* Scalable Analytics Architecture

---

# 💡 Why Parquet?

Parquet is used because it provides:

* Faster query performance
* Columnar storage optimization
* Better compression
* Reduced storage usage
* Efficient analytics processing

---

# 🏆 Key Learnings

Through this project, I learned:

* Building scalable PySpark pipelines
* Processing large datasets efficiently
* Implementing analytical KPIs
* Using Window Functions for ranking
* Exporting optimized analytical datasets
* Integrating Big Data workflows with BI tools

---

# ▶️ How to Run the Project

## 1️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 2️⃣ Start PySpark Environment

Run the notebook in:

* Google Colab
* Jupyter Notebook
* Databricks

---

## 3️⃣ Execute the Pipeline

Run all notebook cells sequentially.

Outputs will be generated in:

```text
data/processed/
```

---

# 📌 Future Improvements

* Deploy pipeline on Databricks
* Add streaming data processing
* Integrate Apache Airflow
* Add cloud storage support
* Automate data ingestion
* Build real-time dashboards

---

# 👨‍💻 Author

Developed by Mohamed
Data Engineering & Analytics Project

---

```
```
"# Football-Data-Engineering-avec-PySpark-Statistiques-KPIs-et-champions" 
