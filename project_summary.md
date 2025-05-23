# Personal Projects Summary

*patcharanat p.*

## Data Science / Data Engineering / Machine Learning Projects

1. 🚀[**End-to-end E-commerce Data Project - AI-Driven Interpretable Dynamic Customer Segmentation**](https://github.com/patcha-ranat/Ecommerce-Invoice-End-to-end)
    - Local and Cloud Environment Setup:
        - Docker | Docker Compose
        - PostgreSQL
            - Initializing Database and Table Input by Entrypoint
        - Airflow
            - Utilizing entrypoint for Airflow `Variables` and `Connections`
            - Authenticating with GCP Artifact Registry within Airflow Entrypoint
    
    - Cloud Provisioning: GCP/AWS by Terraform:
        - GCP: Cloud Storage, BigQuery, Artifact Registry, Workload Identity Federation (WIF).
            - Implemented secure Application Default Credentials (ADC) authentication (short-lived credentials) and service account impersonation for GCP.
            - Cloud Permission Management with IAM and account impersonation.
            - Impersonation does require "Service Account Token Creator" permission
        - AWS: S3 and Redshift (Cluster + Serverless).
    
    - Simulated data sources used in ETL pipelines
        - API OAuth 2.0 for extracting data from Kaggle
        - RestAPI for extracting data from GitHub

    - Data Pipeline
        - Pyspark Ingestion Framework

    - Interactive Analysis Dashboard:
        - Conducted EDA and created a PowerBI dashboard with DAX for in-depth analysis.

    - Machine Learning Development:
        - Data Preprocessing, EDA, and ML Model Output Analysis
            - Correlation
            - Outlier Handling (Z-score / IQR)
        - Cross-Validation
            - RandomSearchCV
        - Interpretable Dynamic customer segmentation
            - RFM
            - KMeans (finding optimal K by calculus derivative)
            - Permutation Feature Importance
            - LightGBM
        - Market Basket Analysis for product recommendations
            - Association Rule
        - Sales forecasting for time series analysis.
            - MinMaxScaler | LightGBM | auto-correlation | Fourier Analysis | Lag | SMA

    - Machine Learning Pipeline
        - Productionized Machine Learning pipelines as containerized Python services using the factory method for precompute serving patterns.
        - Extract ML Logic from notebook to be a module for proper SDLC code
        - Model versioning
        - Re-training by checking explainability performance
        - Implemented DockerOperator for ML services and Airflow integration test
            - GCP ADC and mounting for authentication

    - Model Deployment:
        - Automated CI/CD Pipeline with GitHub Actions (GHA) Workflow:
            - CI: Pytest for unit tests, Ruff for linting, integrated with pre-commit hooks.
            - CD: Keyless authentication (WIF) and ML deployment leveraging Google Artifact Registry (GAR).
        - Keyless Authentication in CI/CD Pipeline
            - Enabled by Workload Identity Federation (WIF) using the JWT concept, URI Link, and assertion condition to authenticate
            - required some cloud service provisioning (WIF provider & Pool)

    - Code Quality and Testing
       - Pre-commit | Ruff | Pytest | Makefile

2. 👍[**MLOps-ml-system**](https://github.com/patcha-ranat/MLOps-ml-system)
    - MBTI-IPIP
        - ML Self-supervised learning
        - Containerized ML application using Streamlit and Docker for ML inference interface.
        - Provisioned Azure cloud resources for ML deployment using a Terraform remote backend.
        - Deployed the ML application on Azure via Azure Web App Service through Azure CLI and a Terraform-integrated CI/CD pipeline.

3. 👍[**Local Airflow K8s Helm**](https://github.com/patcha-ranat/local-airflow-k8s-helm)
    - Deploying Airflow on k8s locally using minikube, helm chart, and sync dag with volume mount (PV/PVC)
    - Additional configuration
        - Increase K8s Resource utilization (RAM)
        - Add a webserver secret key, unless the webserver keeps restarting

4. modern-elt-clouds
    - Terraform - GCP/AWS
        - Authentication: GCP ADC / AWS SSO
    - NoSQL - MongoDB, Firestore, DynamoDB (table) with Python APIs
    - Streaming - Kafka
        - Zookeeper
        - Broker
        - Redpanda Console
        - Schema Registry
        - Rest Proxy
        - Kafka Connect (pre-built producer & consumer)
            - Kafka Connect requires matched serialization-deserialization due to the TCP protocol
            - Kafka Connect doesn’t support AWS SSO
            - Best practice is to use Schema Registry as a data contract
    - Data Preparation - Polars & Data Loader
    - Other possible exploration
        - Scalability & Tolerance (Consumer Parallelization)
        - Implementing Partitioner
        - POC Kafka Connect recovering & rebalancing

5. de-pyspark-airflow
    - Data Ingestion of local parquet files to docker postgresDB using PySpark integrated with Airflow orchestrated by docker-compose.
        - Custom Airflow Operator written in OOP.
        - Extended official airflow docker image by installing pyspark and necessary dependencies (JAVA, JDBC jar file, and python package).

6. ML-Learning
    - Machine learning experiment for learning purpose.
    - Algorithm & ML development/evaluation research and note.
    - Revised AI-driven Interpretable Customer Segmentation ML Development
    - MBTI - IPIP ML Development Process
    - Agentic Workflow (CrewAI)
        - SQLite and RAG

7. kde-zoomcamp
    - Data Engineering Zoomcamp
        - Basics Docker/Docker Compose, Terraform, Airflow, dbt, Pyspark, Kafka
    - MLOps Zoomcamp
        - Mlflow
        - ML Deployment
        - Best Practices
            - Unit Test, Integration Test
    - Data Rockie Streamlit

8. save-canva-link-to-pdf
    - Scraping canva link to create a pdf from it with selenium
        - Using `selenium` to extract image url then convert to PDF
        - Using `pyautogui` to automated capturing slides saved as image then convert to PDF

9. sp-test
    - Pyspark with Business Logic
    - Pyspark SQL setting up

10. TD-Test
    - ETL Pipeline with MongoDB, GCS, Bigquery, Docker, Airflow, and Terraform

11. Big-Data-for-Energy-Management
    - The project introduced understanding of the machine learning model development process, such as cross-validation, hyperparameter tuning, models' algorithm, mostly tree-based models, model evaluation and other techniques such as early stopping, imputation, data pre-processing, and feature engineering.
    - The energy demand inference from regression model can also be used further to cluster the similar energy consumption patterns which might be useful for us knowing the future energy consumption.

## Data Analysis Projects

12. Marketing-Dashboard
13. GrabSpark-Data-Analytics-for-Business-Use-Cases
14. food-retail-strategy
15. Online-Learning-Platform-Analysis
16. Web-Scraping-and-Data-Analytics-PodBean
17. FB-Live-Analysis-Chadchart
18. Crime-REST-API-Machine-Learning
