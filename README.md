# Portfolio 2 — Investment Data Platform (Microsoft Fabric)

## 🎯 Objective
Design and implement an end-to-end **data engineering pipeline** in **Microsoft Fabric** to ingest, transform, and analyze financial market data, following a **Bronze / Silver / Gold** architecture and production-oriented best practices.

This project focuses on **ETL design, Spark transformations, schema enforcement, and analytical modeling**, simulating a real-world data platform.

---

## 🏗️ Architecture Overview

**Bronze → Silver → Gold**

Each layer is fully isolated and reads exclusively from the previous one.

- **Bronze**: Raw data ingestion (JSON)
- **Silver**: Cleaned, normalized, and typed data model
- **Gold**: Analytical layer with financial metrics

The pipeline is orchestrated using **Microsoft Fabric Pipelines**.

---

## 📥 Data Source
- **Alpha Vantage API**
- Endpoint: Daily Time Series
- Format: JSON keyed by date (non-tabular structure)

---

## 🧱 Bronze Layer — Raw Ingestion
**Purpose:** preserve source data exactly as received.

- Stores raw JSON responses from the API
- No transformations applied
- Designed for reprocessing, auditing, and replay
- Data is written to the Lakehouse `Files` area

---

## 🥈 Silver Layer — Clean & Structured Data
**Purpose:** create a reliable, analytics-ready core dataset.

Key transformations:
- Normalization of time-series JSON with dynamic keys (dates)
- Conversion from `STRUCT` to `MAP` for proper explosion
- Explicit schema definition
- One row per asset per trading day
- Strong typing for analytical correctness

Output table:
- silver.fact_asset_price_clean

---

## 🥇 Gold Layer — Analytical Model
**Purpose:** expose business-ready metrics for analysis.

Derived metrics:
- Daily return
- 7-day moving average
- 30-day moving average

Key characteristics:
- Reads exclusively from the Silver layer
- Uses Spark window functions
- Fully deterministic and reproducible

Output table:
- gold.fact_asset_performance

---

## 🔁 Orchestration — Fabric Pipeline
The pipeline orchestrates the full data flow:

1. Bronze ingestion notebook
2. Silver transformation notebook
3. Gold analytical notebook

Characteristics:
- Clear dependencies between layers
- No reliance on in-memory state
- Re-runnable and production-oriented
- Ready for scheduling (daily or on-demand)

---

## 🛠️ Technologies Used
- Microsoft Fabric
- Lakehouse (Delta Lake)
- Apache Spark (PySpark)
- Fabric Pipelines
- REST API ingestion

---

## 🔑 Key Skills Demonstrated
- End-to-end ETL design
- Bronze / Silver / Gold architecture
- Spark data modeling
- JSON normalization with dynamic schemas
- Schema enforcement and data typing
- Window functions for analytics
- Pipeline orchestration in Microsoft Fabric

---

## 📌 Notes
This project is part of a broader **Microsoft Fabric Data Engineering portfolio**, designed to reflect real-world scenarios and interview-level expectations.
