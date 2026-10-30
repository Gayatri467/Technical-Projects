
# MRT BGP Analytics Dashboard

## 1. Introduction

The MRT BGP Analytics Dashboard provides a web-based interface for exploring and analysing historical BGP routing data.

The dashboard uses Flask as the backend, DuckDB for database queries, Apache Parquet for data storage, and Chart.js for visualizing routing statistics.

## 2. Technologies Used

- Python
- Flask
- DuckDB
- Apache Parquet
- DuckDB-WASM
- JavaScript
- Chart.js
- HTML and CSS
- Tailwind CSS

## 3. Dashboard Architecture

The application follows this workflow:

1. Historical MRT routing data is processed and stored in Parquet files.
2. DuckDB reads and queries the processed Parquet data.
3. Flask provides the backend application and API endpoints.
4. The frontend displays analytical results.
5. Chart.js presents routing statistics through interactive visualizations.

## 4. Dashboard Features

The dashboard provides different analytical views of historical BGP routing information.

### 4.1 AS Path Length Analysis

Displays the distribution of AS path lengths in the routing dataset.

### 4.2 Top Peer AS Analysis

Identifies the Autonomous Systems that appear most frequently as peers in the routing data.

### 4.3 Top Prefixes

Displays the most frequently observed IP prefixes in the dataset.

### 4.4 Unique Prefixes Over Time

Shows how the number of unique prefixes changes over time.

### 4.5 BGP Updates Over Time

Displays routing update activity over time using historical BGP update data.

## 5. DuckDB Analytical Queries

DuckDB is used to execute SQL queries on Parquet datasets.

The dashboard uses analytical queries to retrieve routing statistics such as:

- AS path length distribution.
- Top peer AS numbers.
- Frequently observed prefixes.
- Unique prefix counts.
- BGP update counts over time.

These query results are passed to the frontend for visualization.

## 6. Running the Dashboard

Navigate to the project directory:

```bash
cd ~/projects/mrt-duckdb-analytics
```

Start the Flask application:

```bash
python api.py
```

The application runs on the configured Flask port.

Open the dashboard in a web browser using the application address.

For example:

```text
http://127.0.0.1:5000
```

If another port is configured, use that port instead.

## 7. Dashboard Output

The dashboard displays analytical results using charts and visual elements.

The outputs help users understand:

- BGP routing path characteristics.
- Frequently observed peer AS numbers.
- Prefix distribution.
- Changes in unique prefixes over time.
- Historical BGP update activity.

## 8. Conclusion

The MRT BGP Analytics Dashboard provides a visual interface for analysing large historical routing datasets.

By integrating Flask, DuckDB, Parquet, and Chart.js, the project makes BGP routing statistics easier to query, explore, and understand.
