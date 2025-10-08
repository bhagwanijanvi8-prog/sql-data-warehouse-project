# 🏗️ SQL Data Warehouse from Scratch | Full Hands-On Data Engineering Project

## 📘 Overview

This project demonstrates how to design, build, and optimize a **Data Warehouse from scratch** using pure **SQL**.  
It covers every stage of the data engineering lifecycle — from **data extraction** and **cleansing** to **modeling**, **ETL**, and **reporting** — following the **Medallion Architecture** (Bronze → Silver → Gold).

The goal is to create a **robust, scalable, and maintainable data warehouse** that serves as a single source of truth for analytical and business reporting.

---

## 🧩 Key Concepts & Fundamentals

- **Data Warehouse Purpose:** Centralized system for integrating multiple data sources to enable historical analysis and consistent reporting.
- **ETL Process:** Core of warehouse development, involving heavy transformations like cleansing, normalization, and integration.
- **Architecture Choices:** Inmon, Kimball, Data Vault, and Medallion architectures (this project uses **Medallion**).
- **Data Management Approaches:** Warehouse, Lake, Lakehouse, or Mesh — each suited to different use cases.

---

## 🏛️ Medallion Architecture Overview

| Layer | Purpose | Audience | Example Tasks |
|:------|:---------|:----------|:---------------|
| 🥉 **Bronze** | Raw data from source systems | Data Engineers | Extraction, bulk load, incremental loading |
| 🥈 **Silver** | Cleaned & standardized data | Engineers / Analysts | Deduplication, normalization, validation |
| 🥇 **Gold** | Business-ready data | Analysts / BI Users | Aggregation, enrichment, business transformations |

---

## ⚙️ ETL Workflow

### 🔹 1. Data Extraction & Loading
- Methods: database connections, file parsing, APIs, event streams, and change data capture.
- Loading: batch and stream processing (truncate-insert, upsert, or drop-create).
- Bulk load CSVs directly into bronze tables for performance.

### 🔹 2. Data Transformation & Cleansing
- Remove duplicates, handle nulls, and standardize data.
- Use SQL functions: `TRIM()`, `REPLACE()`, `ROW_NUMBER()`, and `LEAD()` for quality assurance.
- Validate date ranges, data types, and business rules.

### 🔹 3. Data Modeling
- **Star Schema** in Gold Layer:
  - **Fact Tables:** transactional or event data.
  - **Dimension Tables:** descriptive entities.
- **Surrogate Keys:** replace natural keys using `ROW_NUMBER()` for consistent joins.

---

## 🧱 Data Warehouse Design Principles

1. Data flows **bronze → silver → gold** only (no shortcuts).  
2. Add **DW_*** prefix to metadata columns (e.g., `DW_CreateDate`).  
3. Maintain **data lineage diagrams** for full traceability.  
4. Implement **quality gates** after each ETL phase.  
5. Use **views** instead of physical tables in the gold layer for flexibility.

---

## 📊 Quality & Documentation

- **Data Lineage Diagrams:** visualize flow from sources to gold layer.
- **Data Catalog:** documents table purpose, columns, and relationships.
- **Data Quality Checks:** uniqueness, foreign key integrity, null checks, and record count validation.
- **Logging:** track file source, load times, and errors for debugging.

---

## 🧠 Advanced Concepts

- **Slowly Changing Dimensions (SCD):** manage historical records using SCD0, SCD1, and SCD2.
- **Change Data Capture (CDC):** efficiently track and load data changes.
- **Parallel Processing:** improve ETL performance on large datasets.
- **Partitioning:** optimize table storage and query performance by date or region.

---

## 🧰 Tech Stack

| Category | Tools / Technologies |
|:----------|:---------------------|
| Database | SQL Server / PostgreSQL / Snowflake (choose one) |
| ETL | Pure SQL scripts, Stored Procedures |
| Version Control | Git + GitHub |
| Documentation | Notion / Markdown |
| Visualization | Power BI / Tableau (optional) |

---

## 🚀 Project Setup

1. Clone this repository  
   ```bash
   git clone https://github.com/yourusername/sql-data-warehouse.git
   cd sql-data-warehouse

