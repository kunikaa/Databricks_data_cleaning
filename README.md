#  NYC Taxi Data Analysis | PySpark + Databricks

##  Overview
An end-to-end data analysis pipeline built on Databricks using PySpark,
processing NYC Taxi trip records through data cleaning, feature engineering,
and Spark SQL analytics to extract real business insights.

---

##  Dataset
- **Source:** `samples.nyctaxi.trips` — built into every Databricks workspace
- **Domain:** NYC Yellow Taxi Trip Records
- **Columns used:** pickup/dropoff datetime, fare amount, trip distance

---

##  What This Project Does

###  Stage 1 — Data Cleaning
- Removed null values → `dropna()`
- Removed duplicate records → `dropDuplicates()`
- Filtered outliers:
  - Fare between **$1 – $200**
  - Distance between **0.1 – 50 miles**
- Record-count printed after every step for full observability

###  Stage 2 — Feature Engineering
| New Column | What It Means |
|---|---|
| `trip_duration_mins` | How long the trip took in minutes |
| `fare_per_mile` | How expensive the trip was per mile |
| `is_rush_hour` | 1 if pickup was 7–9am or 5–7pm, else 0 |

###  Stage 3 — Spark SQL Analytics
| # | Analysis | Business Question Answered |
|---|---|---|
| 1 | Peak Demand Hours | When are taxis busiest? |
| 2 | Daily Revenue Trend | How does revenue change day to day? |
| 3 | Weekday vs Weekend | Do riders behave differently on weekends? |
| 4 | Fare Segmentation | What share of trips are budget vs premium? |

---

##  Key Insights
- Morning (7–9am) and evening (5–7pm) are peak demand windows
- Daily revenue fluctuates significantly across the week
- Weekend trips tend to be longer with higher average fares
- Majority of trips fall in the Budget (< $10) fare tier

---

##  Tech Stack
| Tool | Purpose |
|---|---|
| **PySpark** | Distributed data processing |
| **Apache Spark** | Cluster computing engine |
| **Databricks** | Cloud notebook platform |
| **Spark SQL** | Business analytics queries |
| **Python 3.11** | Core language |

---

##  How to Run
1. Open [Databricks Community Edition](https://community.cloud.databricks.com) *(free)*
2. Create a cluster — DBR 12+ recommended
3. Import `csv_cleaning.ipynb` into your workspace
4. Attach cluster → Click **Run All**

> **Note:** No data download needed.
> `samples.nyctaxi.trips` is available in every Databricks workspace by default.

---

