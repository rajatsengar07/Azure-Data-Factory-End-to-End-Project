# Azure Data Factory End-to-End Data Pipeline

## Overview
An end-to-end cloud data integration pipeline built using Azure Data Factory, ADLS Gen2, and Mapping Data Flows to process and transform raw booking and airline data into a structured Medallion Architecture (Bronze -> Silver -> Gold layers).

## Architecture & Workflow
1. **Ingestion (Bronze):** Ingest raw booking data from source landing zones into Azure Data Lake Storage Gen2.
2. **Transformation (Silver):** Perform schema joins (`Left Outer Join` on Fact/Dim tables) and field cleanup using ADF Data Flows.
3. **Aggregation & Ranking (Gold):** Aggregate total sales per airline, compute ranking metrics using `denseRank()`, and filter top-performing airlines.
4. **CI/CD Integration:** Source-controlled via GitHub with automated publishing.

## Key Features
* Dynamic Data Flow orchestration using Window functions (`denseRank()`).
* Medallion Lakehouse Architecture design pattern.
* Complete parameterization and integration with Self-Hosted / Azure Integration Runtimes.

## How to Deploy
1. Clone this repository.
2. Import the JSON definitions in the `/pipeline`, `/dataflow`, and `/dataset` folders directly into your Azure Data Factory workspace.
