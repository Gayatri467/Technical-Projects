# Technical-Projects
Technical projects documentation and step-by-step guides for projects developed and researched.
# Technical Projects Documentation

## Overview

This repository contains technical documentation for projects developed and researched as part of technical learning and project assignments.

The purpose of this repository is to provide clear, step-by-step instructions that help developers and colleagues understand the projects, configure the required tools, execute the applications, and verify the results.

## Projects

### 1. FRR and MRT Lab
Development of a containerized BGP routing laboratory using FRRouting (FRR) and Docker Compose. The project focuses on configuring routing environments, running BGP services in containers, and exploring MRT-based routing data generation and collection for further analysis.

### 2. MRT-Based BGP Routing Data Analytics Using DuckDB and Parquet
Development of a data analytics pipeline for processing historical BGP routing information obtained from MRT datasets. The project involves importing routing data, merging datasets from multiple sources, identifying and removing duplicate records, and storing the processed data in Apache Parquet format. DuckDB is used to perform analytical queries, generate routing statistics, and support an interactive web dashboard developed using Flask.

### 3. Authentication and Telemetry Experiments
Exploration of application authentication and observability technologies through ZITADEL and OpenID Connect (OIDC) integration. The work includes configuring an authentication application, setting up login and redirect URLs, and testing the authentication flow. OpenTelemetry components were also explored as part of a separate telemetry experiment.

### 4. Kubernetes Deployment
Deployment and management of the MRT DuckDB Analytics application in a Kubernetes environment. This project covers containerized application deployment, Kubernetes Deployments and Services, NodePort configuration, pod management, application accessibility, and deployment verification.

### 5. BGPalerter Monitoring
Study, configuration, and testing of BGPalerter for monitoring live BGP routing updates through the RIPE RIS Live streaming service. The work includes configuring monitored prefixes and ASNs, enabling monitoring modules.

## Technologies and Tools Used

- Python – Application development and data processing.
- DuckDB – Querying and analysing routing data.
- Apache Parquet – Storing processed routing datasets.
- Flask – Building the web dashboard.
- SQL – Data analysis and querying.
- Docker – Containerizing applications and running isolated environments.
- Docker Compose – Managing multi-container environments.
- Kubernetes – Deploying and managing containerized applications.
- BGPalerter – Monitoring live BGP routing updates.
- FRRouting (FRR) – Building and testing BGP routing environments.
- ZITADEL – Authentication and identity management.
- OpenID Connect (OIDC) – Authentication protocol.
- OpenTelemetry – Telemetry experiments.
- Linux / Ubuntu – Development and execution environment.
- Git and GitHub – Version control and documentation management.

## Documentation Structure

Each project has a separate folder containing its overview, setup instructions, configuration details, execution steps, expected outputs, and troubleshooting information.

## Purpose

This repository serves as a technical reference for understanding, maintaining, and reproducing the documented projects.

