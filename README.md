# README.md

````markdown
# NYC Yellow Taxi Trip Data Analysis using Apache Spark

## Overview

This project is a comprehensive big data analytics case study using Apache Spark to analyze the NYC Yellow Taxi Trip dataset. The project compares the performance of three Spark APIs:

- RDD API
- DataFrame API
- Spark SQL

The analysis focuses on performance optimization, query execution, window functions, joins, caching, and file format optimization using Parquet.

The project was developed as part of the Big Data Analytics course.

---

# Project Structure

```bash
NYC-Taxi-Spark-Analysis/
│
├── notebook/
│   ├── Query1_Filtering.ipynb
│   ├── Query2_Aggregation.ipynb
│   ├── Query3_Revenue_By_Hour.ipynb
│   ├── Query4_Top_Trips.ipynb
│   ├── Query5_Moving_Average.ipynb
│   ├── Query6_Above_Average_Fare.ipynb
│   ├── Query7_Join_Optimization.ipynb
│   ├── Query8_Cumulative_Revenue.ipynb
│   ├── Query9_Busiest_Zones.ipynb
│   └── Query10_Parquet_vs_CSV.ipynb
│
├── data/
│   └── yellow_tripdata_2015-01.csv
│
├── report/
│   └── Mini_Project_2_Report.pdf
│
└── README.md
````

---

# Dataset Information

* **Dataset:** NYC Yellow Taxi Trip Data
* **Source:** Kaggle
* **Records:** ~11.4 million taxi trips
* **Format:** CSV and Parquet
* **Period:** January 2015

### Main Attributes

* VendorID
* Pickup/Dropoff Datetime
* Passenger Count
* Trip Distance
* Fare Amount
* Payment Type
* Tip Amount
* Total Amount

---

# Project Objectives

* Analyze large-scale taxi trip data using Apache Spark
* Compare Spark APIs performance
* Apply Spark optimization techniques
* Implement analytical and window queries
* Evaluate file format impact on performance
* Study Catalyst optimizer behavior

---

# Technologies Used

* Python
* Apache Spark
* PySpark
* Jupyter Notebook
* Spark SQL
* Pandas
* Parquet
* Hadoop Ecosystem Concepts

---
# Dataset Download

The dataset is too large to upload directly to GitHub.

You can download it from Kaggle:

[NYC Yellow Taxi Trip Data Dataset](https://www.kaggle.com/datasets/elemento/nyc-yellow-taxi-trip-data)

File used in this project:
- `yellow_tripdata_2015-01.csv`

After downloading, place the dataset inside the `data/` folder.

---

# Queries Implemented

## Query 1 — Complex Filtering

Trips with:

* Fare amount > $20
* Passenger count > 1

### Concepts

* Filtering
* Predicate Pushdown
* Performance Comparison

---

## Query 2 — Aggregations per Payment Type

Performed:

* SUM
* AVG
* COUNT
* MAX
* MIN

### Concepts

* Aggregation
* HashAggregate
* Catalyst Optimization

---

## Query 3 — Revenue by Hour and Vendor

Grouped revenue based on:

* Pickup hour
* VendorID

### Concepts

* Multi-column GROUP BY
* Aggregation Optimization

---

## Query 4 — Top 10 Most Expensive Trips

Sorted trips by fare amount descending.

### Concepts

* Sorting
* Ranking
* TakeOrdered Optimization

---

## Query 5 — 7-Day Moving Average

Calculated sliding window averages for daily fares.

### Concepts

* Window Functions
* Distributed Processing

---

## Query 6 — Trips Above Average Fare

Identified trips exceeding the average fare within each rate code.

### Concepts

* Nested Subqueries
* BroadcastHashJoin

---

## Query 7 — Broadcast Join vs Sort-Merge Join

Compared join strategies for borough enrichment.

### Concepts

* Broadcast Join
* Sort-Merge Join
* Shuffle Optimization

---

## Query 8 — Cumulative Daily Revenue

Computed running totals of daily revenue.

### Concepts

* Window Functions
* Cumulative Sum

---

## Query 9 — Busiest Pickup Zones

Found top pickup zones by day of week.

### Concepts

* Ranking Functions
* Distributed Top-N Queries

---

## Query 10 — CSV vs Parquet Benchmark

Compared:

* CSV
* Parquet
* Cached Parquet
* Partitioned Parquet

### Concepts

* Columnar Storage
* Partition Pruning
* Caching
* Predicate Pushdown

---

# Performance Highlights

| Query             | Fastest API |
| ----------------- | ----------- |
| Filtering         | DataFrame   |
| Aggregations      | Spark SQL   |
| Grouping          | DataFrame   |
| Sorting           | Spark SQL   |
| Window Functions  | DataFrame   |
| Nested Queries    | Spark SQL   |
| Join Optimization | DataFrame   |
| Cumulative Sum    | DataFrame   |
| Ranking           | Spark SQL   |
| Parquet Benchmark | DataFrame   |

---

# Key Insights

* DataFrame and Spark SQL significantly outperform RDD.
* Catalyst Optimizer greatly improves execution efficiency.
* Broadcast joins reduce shuffle cost.
* Window functions are highly optimized in Spark SQL/DataFrames.
* Parquet format dramatically improves performance.
* Partition pruning and caching provide major speedups.

---

# Installation

## Clone Repository

```bash
git clone https://github.com/Mariam-1611/NYC-Yellow-Taxi-Trip-Data-Analysis-using-Apache-Spark.git
cd nyc-taxi-spark-analysis
```

---

## Install Dependencies

```bash
pip install pyspark pandas jupyter
```

---

# Running the Project

## Start Jupyter Notebook

```bash
jupyter notebook
```

Then open notebooks from the `notebook/` folder.

---

# Spark Optimization Techniques Used

## Catalyst Optimizer

* Predicate Pushdown
* Projection Pruning
* Join Reordering
* Physical Plan Optimization

## Tungsten Engine

* Whole-stage code generation
* Binary memory management

## Join Optimization

* BroadcastHashJoin
* SortMergeJoin

## Storage Optimization

* Parquet Format
* Partition Pruning
* In-memory Caching

---

# Analytical Findings

* Credit card payments dominate taxi transactions.
* Evening hours generate the highest revenue.
* Manhattan and Midtown are the busiest pickup zones.
* Partitioned Parquet storage achieved up to 11.5x speedup over CSV.
* RDD consistently showed the slowest execution times.

---

# Learning Outcomes

This project strengthened understanding of:

* Big Data Analytics
* Apache Spark APIs
* Distributed Data Processing
* Query Optimization
* Window Functions
* Join Strategies
* Storage Optimization
* Performance Benchmarking

---

# Authors

* Mariam Mohamed Goda
* Yasmin Osama

---

# License

This project is for educational purposes only.

```
```
