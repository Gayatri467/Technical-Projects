
# MRT-Based BGP Routing Data Analytics Using DuckDB and Parquet

## Overview

This project focuses on processing and analysing historical BGP routing data obtained from MRT datasets.

It uses Apache Parquet for efficient storage and DuckDB for analytical SQL queries. A Flask-based web dashboard provides visualizations of routing statistics.

## Project Objectives

- Process historical MRT routing datasets.
- Merge RIPE RIS and RouteViews routing data.
- Identify and remove duplicate routing records.
- Store processed data in Parquet format.
- Perform analytical queries using DuckDB.
- Visualize BGP routing statistics through a web dashboard.

## Technologies Used

- Python
- DuckDB
- Apache Parquet
- Flask
- Chart.js
- Tailwind CSS
- bgpdump

## Documentation

1. [Data Processing Guide](Data-Processing.md) – MRT data extraction, merging, duplicate removal, and Parquet generation.
2. [Dashboard Guide](Dashboard.md) – Flask application, DuckDB queries, visualizations, and dashboard execution.

## Project Workflow

MRT Datasets → Data Extraction → Merging → Duplicate Removal → Parquet Storage → DuckDB Analytics → Flask Dashboard

## Project Outcome

Successfully processed historical BGP routing datasets, generated merged and deduplicated Parquet files, and developed a web dashboard to explore BGP routing statistics.

## Note

This project focuses on historical MRT data analytics. Live BGP monitoring using BGPalerter is documented separately.

