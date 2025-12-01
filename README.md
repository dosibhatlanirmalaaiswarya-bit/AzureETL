# End-to-End Azure Data Engineering Project 🚀

A full-stack data engineering pipeline built with Azure Data Factory (ADF), Azure Databricks, and Azure Data Lake, designed to ingest, transform, and deliver analytics-ready data for downstream BI and ML use cases. This project focuses on production-style patterns: orchestration, medallion architecture, and scalable data transformations. 

---

## Business Problem

Analytics teams often work with scattered source systems (ERP, CRM, flat files, APIs) and manual data refreshes, making it difficult to maintain a single, trusted view of business performance. This project demonstrates how to use Azure-native tools to automate ingestion, transformations, and delivery of curated data layers for reliable reporting and advanced analytics.

---

## Technical Overview

This repository implements an end-to-end Azure data engineering workflow that:

- Ingests raw data from one or more source systems (e.g., CSV/Blob storage, operational databases, APIs) into a raw “bronze” layer.
- Cleanses, validates, and transforms data in Azure Databricks using Spark, producing curated “silver” and “gold” tables.
- Stores data in a lakehouse-style architecture (Azure Data Lake / Delta Lake) to support batch analytics and potential ML workloads.
- Exposes modeled gold-layer tables to Power BI (or any BI tool) for KPI tracking and business dashboards. [attached_file:1]

The emphasis is on reusable patterns (orchestration, layering, data quality) rather than any single dataset.

---

## Architecture
![DataArchitecture](https://github.com/dosibhatlanirmalaaiswarya-bit/Azure-Based-ETL-Pipeline-Using-ADF-Databricks/blob/081145f8fa6e4921ba4f6a7ab98054a8a74e9cd9/Azure%20Architecture%20Diagram.jpg)
### Components

| Component                        | Responsibility                                                                 |
|----------------------------------|-------------------------------------------------------------------------------|
| Azure Data Factory (ADF)        | Orchestrates pipelines, scheduling, triggers, and data movement              |
| Azure Databricks                | Executes PySpark notebooks for cleansing, joins, aggregations, business logic|
| Azure Data Lake / Delta Lake    | Stores bronze, silver, and gold data layers with partitioning as needed      |
| Power BI (optional)             | Connects to gold tables/views for dashboards and self-service analytics      | 

### Medallion Architecture

- Bronze: Raw ingested data, minimally processed, stored as-is from source.
- Silver: Cleaned, conformed data with standardized types, deduplication, and basic business rules.
- Gold: Aggregated, analytics-ready tables optimized for reporting and KPI monitoring.

---

## Data Engineering Features

- End-to-end ETL/ELT pipeline built on Azure (ADF + Databricks + Data Lake).
- Medallion architecture (Bronze → Silver → Gold) for clear lineage and separation of concerns.
- Parameterized ADF pipelines for reusable ingestion patterns and environment-specific configuration.
- PySpark transformations for:
  - Data cleansing and type casting.
  - Joins across multiple sources.
  - Incremental loads and aggregations for KPI

