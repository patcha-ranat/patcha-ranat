# Note for Professional Google Cloud Data Engineer Learning Path

*patcharanat p.*

## Table of Contents

1. [Introduction to Data Engineering on Google Cloud](#1-introduction-to-data-engineering-on-google-cloud)
    - [1.1 Course Introduction](#11-course-introduction)
    - [1.2 Data Engineering Tasks and Component](#12-data-engineering-tasks-and-component)
    - [1.3 Data Replication and Migration](#13-data-replication-and-migration)
    - [1.4 The Extract and Load Data Pipeline Pattern (EL)](#14-the-extract-and-load-data-pipeline-pattern-el)
    - [1.5 The Extract, Load, and Transform Data Pipeline Pattern (ELT)](#15-the-extract-load-and-transform-data-pipeline-pattern-elt)
    - [1.6 The Extract, Transform, Load Data Pipeline Pattern (ETL)](#16-the-extract-transform-load-data-pipeline-pattern-etl)
    - [1.7 Automation Techniques](#17-automation-techniques)
    - [1.8 Course Summary](#18-course-summary)

## 1. Introduction to Data Engineering on Google Cloud

### 1.1 Course Introduction

This section welcomes you to the Introduction to Data Engineering on Google Cloud course, and provides an overview of the course structure and goals.

### 1.2 Data Engineering Tasks and Component

This module provides an introduction to the role of a data engineer. It covers key concepts such as data sources and sinks, data formats, storage options on Google Cloud, metadata management, and the use of Analytics Hub for data sharing within and outside an organization.
- A data engineer builds data pipelines to enable data-driven decisions
- Data engineering tasks evolve around ingesting, transforming, and storing data
- Unstructure Data Storage - **Google Cloud Storage (GCS)**
    - can be accessed by HTTP requests
    - max object size = 5 TB
    - retrived by object name
    - Standard Storage = Application data
    - Nearline Storage = Database backups
    - Coldline Storage = Log files
    - Archive Storage = Compliance data
- Structure Data Storage
    - Transactional Workload SQL
        - SQL
            - **Cloud SQL**: Managed relational database service (RDBMS)
            - **AlloyDB**: Fully managed, high-performance PostgreSQL DB
            - **Spanner**: Fully managed relational database service, offering consistency and horizontal scalability
        - NoSQL
            - **Firestore**: Fully managed, serverless, NoSQL document database built for automatic scaling and high performance
    - Analytical Workload
        - SQL
            - **BigQuery**: Full managed, serverless data warehouse
                - BI, ML, project-dataset-table
                - bq command line tool included in Google Cloud SDK, REST API, Web-based SQL editor
                - Access control is through IAM with dataset, table, view, or column level 
        - NoSQL
            - **Bigtable**: fast key-value lookup
- Metadata is a key element to make data more manageable and useful across organization
    - **Dataplex**: comprehensive data management solution
        - Data to AI governance
        - Data governance in BigQuery
        - Insights and semantic search
        - Data Discovery and Data Catalog
        - End-to-end data lineage
- **Analytic Hub**: Address data sharing challenges between organizations by enabling publish-subscrie method to shared BigQuery datasets
    - data providers are able to control and monitor how their data is being used

### 1.3 Data Replication and Migration

This module provides an overview of data replication and migration on Google Cloud. It covers the basic architecture, the 'gcloud' command-line tool, Storage Transfer Service, Transfer Appliance, and Datastream, along with their functionalities and use cases.



### 1.4 The Extract and Load Data Pipeline Pattern (EL)

This module focuses on data extraction and loading processes on Google Cloud, particularly with BigQuery. It covers the basic extraction and loading architecture, the bq command-line tool, BigQuery Data Transfer Service, and BigLake as an alternative to traditional extract-load patterns.

### 1.5 The Extract, Load, and Transform Data Pipeline Pattern (ELT)

This module provides an overview of ELT (extract, load, transform) processes on Google Cloud. It covers the basic ELT architecture, a common ELT pipeline example, BigQuery's capabilities for scripting and scheduling SQL, and the functionality and use cases of Dataform.

### 1.6 The Extract, Transform, Load Data Pipeline Pattern (ETL)

This module provides an overview of ETL (extract, transform, load) processes on Google Cloud. It covers the basic ETL architecture, GUI tools, batch and streaming data processing options (Dataproc, Dataproc Serverless), and the role of Bigtable in data pipelines.

### 1.7 Automation Techniques

This module focuses on automation patterns and options for pipelines on Google Cloud. It covers various tools and services like Cloud Scheduler, Workflows, Cloud Composer, Cloud Run functions, and Eventarc, along with their functionalities and use cases for automation.

### 1.8 Course Summary

In this final section, we review what was presented in this course and discuss the next steps to continue your cloud learning journey.
