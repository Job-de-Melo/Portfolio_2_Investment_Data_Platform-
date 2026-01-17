# Portfolio 2 — Investment Data Platform (Microsoft Fabric)

## Overview
This project implements an end-to-end data engineering platform for financial market data using Microsoft Fabric.

The goal is to design and build a production-oriented data platform capable of ingesting, transforming, and modeling daily market data (ETFs), following modern data engineering best practices.

This is not a simple investment tracker, but a scalable data platform designed to support analytical and decision-making use cases.

---

## Project Objectives
- Ingest real financial market data from public APIs
- Implement a Lakehouse architecture using Microsoft Fabric
- Apply Medallion Architecture (Bronze, Silver, Gold)
- Build analytics-ready datasets for financial analysis
- Demonstrate end-to-end data engineering skills

---

## Data Source
- **Source:** Public financial market API
- **Dataset:** Daily adjusted prices for ETFs
- **Frequency:** Daily
- **Granularity:** One record per asset per day

---

## Architecture
The platform is built using a Lakehouse architecture with Medallion layers:

- **Bronze:** Raw data ingestion from APIs (JSON format)
- **Silver:** Cleaned and standardized data
- **Gold:** Analytics-ready datasets with financial metrics

A detailed architecture description is available in the documentation folder.

---

## Data Model
The analytical model follows a star schema optimized for time-series analysis.

### Fact Table
- `fact_asset_price` (daily grain: one asset per day)

### Dimensions
- `dim_asset`
- `dim_date`
- `dim_market`
- `dim_currency`

Financial metrics such as daily and cumulative returns are calculated in the Gold layer.

---

## Technology Stack
- Microsoft Fabric
  - Lakehouse
  - Data Pipelines
  - Notebooks (PySpark & SQL)
- Public Financial APIs
- Power BI (analytics consumption)
- GitHub (version control & documentation)

---

## Project Roadmap
- **Week 1:** Data source integration, repository setup, Bronze ingestion
- **Week 2:** Silver transformations and data standardization
- **Week 3:** Gold modeling and financial metrics
- **Week 4:** Power BI consumption and documentation

A detailed roadmap is available as a PDF in the documentation folder.

---

## What This Project Demonstrates
- End-to-end data engineering design
- API-based data ingestion
- Lakehouse and Medallion Architecture implementation
- Analytical data modeling for financial use cases
- Microsoft Fabric applied in a realistic scenario

---

## Status
🚧 In progress
