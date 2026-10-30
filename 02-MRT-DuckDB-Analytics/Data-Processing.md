
# MRT Data Processing Using DuckDB and Parquet

## 1. Introduction

This document explains the processing of historical BGP routing data obtained from MRT (Multi-threaded Routing Toolkit) datasets.

The project uses MRT files as input, converts and processes routing information, stores the results in Apache Parquet format, and uses DuckDB for analytical operations.

## 2. Prerequisites

The following tools and technologies are required:

- Linux / Ubuntu
- Python
- bgpdump
- Apache Parquet
- DuckDB
- Required Python libraries

## 3. Dataset Preparation

Historical BGP routing datasets are collected from RIPE RIS and RouteViews.

The datasets used in this project include:

- RIPE RIS RRC01 BGP routing table dump.
- RouteViews BGP routing table dump.
- BGP update data.

Example input files:

```text
ris.bview.20260903.0800.gz
routeviews.rib.20260903.0800.bz2
updates.20260902.0000.gz
```

These files contain routing information such as IP prefixes, AS paths, and BGP routing updates.

## 4. MRT Data Processing

MRT files are processed to extract routing information.

The `bgpdump` utility is used to read MRT data and convert routing records into a structured format that can be processed further.

The extracted information is prepared for merging and analytical processing.

## 5. Merging Routing Datasets

The RIPE RIS and RouteViews routing datasets are combined to create a consolidated routing dataset.

This process helps bring routing information from different sources into a common dataset for analysis.

Both the merged data and the deduplicated data are retained for comparison.

## 6. Duplicate Removal

Duplicate routing records can occur when combining datasets from different sources.

To handle this, a duplicate removal process is implemented.

The process uses hash-based bucketing to divide records into smaller groups before identifying duplicate entries.

The workflow uses 256 buckets to distribute records and perform deduplication efficiently.

This reduces duplicate records while preserving unique routing information.

## 7. Parquet File Generation

Apache Parquet is used to store the processed routing data.

Parquet is a columnar storage format that provides efficient data storage and analytical query performance.

The project generates:

- Merged Parquet dataset containing the combined routing records.
- Deduplicated Parquet dataset containing unique routing records.

These files are used as the input for DuckDB analytical queries.

## 8. DuckDB Integration

DuckDB is used to query and analyse the generated Parquet files.

It allows SQL queries to be executed directly on Parquet datasets without requiring a separate database server.

The project uses DuckDB to perform analytical operations on historical BGP routing information.

## 9. Processing Results

The following results were obtained during the data processing workflow:

| Processing Stage | Number of Records |
|---|---:|
| Merged dataset | 54,188,497 |
| Deduplicated dataset | 52,548,920 |
| Duplicate records removed | 1,639,577 |

The results show that duplicate removal reduced the number of records while retaining unique routing entries.

## 10. Processing Workflow

The overall processing workflow is:

1. Collect historical MRT datasets.
2. Extract routing information using bgpdump.
3. Combine RIPE RIS and RouteViews datasets.
4. Generate the merged dataset.
5. Divide records into hash-based buckets.
6. Identify and remove duplicate records.
7. Generate Parquet files.
8. Load and analyse the Parquet data using DuckDB.

## 11. Conclusion

The project demonstrates how historical BGP routing data can be processed and analysed using DuckDB and Apache Parquet.

The merging and duplicate removal process creates a consolidated dataset, while Parquet provides efficient storage and DuckDB supports analytical queries over large routing datasets.
