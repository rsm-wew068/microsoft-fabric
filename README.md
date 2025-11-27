# Microsoft Fabric Data Engineering Notebooks

This repository contains Synapse Notebooks designed for **Microsoft Fabric**, demonstrating core data engineering capabilities using **Apache Spark** and **Delta Lake**. These notebooks serve as comprehensive tutorials for building modern data pipelines, from ingestion and transformation to storage and analysis.

## 1. [Spark Data Engineering & Analytics](spark/SynapseNotebook/15091e7a-8c7f-4004-92e5-c8a828082ef4/Notebook_1/spark.ipynb)

This notebook provides an end-to-end workflow for processing sales order data, covering the entire lifecycle from raw CSV ingestion to visual analytics.

### 🔑 Key Features
*   **Data Ingestion & Schema Enforcement**:
    *   Reads raw CSV files (`2019.csv` and others) using PySpark.
    *   Defines strict `StructType` schemas to ensure data quality and type safety.
*   **Data Transformation (ETL)**:
    *   Performs data cleaning and feature engineering (e.g., splitting names, extracting date parts).
    *   Implements partitioning strategies (by Year/Month) to optimize storage and query performance.
    *   Saves transformed data as **Parquet** files.
*   **SQL Analysis**:
    *   Registers DataFrames as temporary views to run complex SQL queries.
    *   Calculates key business metrics like **Gross Revenue** and yearly order counts.
*   **Visualization**:
    *   Converts Spark DataFrames to Pandas for compatibility with standard plotting libraries.
    *   Generates insights using **Matplotlib** and **Seaborn** (Bar charts, Line charts, Pie charts).

**Technologies:** Apache Spark, PySpark, Spark SQL, Parquet, Matplotlib, Seaborn.

---

## 2. [Delta Lake Deep Dive](6249eae6-fc7e-45c9-860a-99d65a209d51/SynapseNotebook/739419bb-2294-44c9-b9dd-ad54cb5f33ce/delta_notebook/delta_notebook.ipynb)

This notebook focuses specifically on the advanced capabilities of **Delta Lake**, the storage foundation of the Microsoft Fabric Lakehouse.

### 🔑 Key Features
*   **Managed vs. External Tables**:
    *   Demonstrates creating **Managed Tables** (fully handled by Fabric) and **External Tables** (data stored in specific OneLake paths).
    *   Uses `DESCRIBE FORMATTED` to inspect table architecture.
*   **Time Travel & Versioning**:
    *   Executes `UPDATE` operations (e.g., a 10% price reduction campaign).
    *   Uses `DESCRIBE HISTORY` to audit transaction logs.
    *   Queries historical data versions using `versionAsOf`, enabling rollback and audit capabilities.
*   **Real-Time Streaming**:
    *   Implements a **Structured Streaming** pipeline ingesting simulated IoT device data (JSON).
    *   Writes streaming data to a Delta sink with checkpointing for fault tolerance.
*   **Hybrid Analytics**:
    *   Combines PySpark for data manipulation with SQL magic commands (`%%sql`) for analysis.

**Technologies:** Delta Lake, OneLake, Structured Streaming, ACID Transactions, Time Travel.

---

## 🚀 Getting Started

To run these notebooks:
1.  Import them into your **Microsoft Fabric** workspace.
2.  Ensure you have a **Lakehouse** attached to the notebook session.
3.  For `delta_notebook.ipynb`, ensure the necessary `products.csv` file is available in your Lakehouse Files.
4.  For `spark.ipynb`, ensure the `orders` dataset is available.
