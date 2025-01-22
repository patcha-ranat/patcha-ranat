# Personal Projects List

*patcharanat p.*

## Data Science / Data Engineering / Machine Learning Projects

- 🚀[**End-to-end E-commerce Data Project - AI-Driven Interpretable Dynamic Customer Segmentation**](https://github.com/patcha-ranat/Ecommerce-Invoice-End-to-end)
    - End-to-end Data project in the e-commerce and retail industries covering the full process of data exploitation, including Data Engineering, Data Science, Data Analytic, and how to automate ML deployment (MLOps). This project covered the entire data lifecycle, from setting up ETL pipelines to deploying AI solutions.
        - Local and Cloud Environment Setup:
            - Built and configured local environments using Docker Compose with Airflow and PostgresDB.
            - Enabled cloud infrastructure using Terraform for GCP and AWS, including:
            - GCP: Cloud Storage, BigQuery, Artifact Registry, Workload Identity Federation (WIF).
            - AWS: S3 and Redshift (Cluster + Serverless).
            - Implemented secure Application Default Credentials (ADC) authentication with no long-lived credentials and service account impersonation.

        - Interactive Analysis Dashboard:
            - Conducted EDA and created a Power BI dashboard with DAX for in-depth analysis.

        - Machine Learning Development:
            - Dynamic customer segmentation with RFM, K-Means, LightGBM, and permutation feature importance.
            - Association rules (Market Basket Analysis) for product recommendations.
            - Sales forecasting using LightGBM for time series analysis.

        - Model Deployment:
            - Productionized Machine Learning pipelines as containerized Python services using the factory method for precompute serving patterns.
            - Automated CI/CD with GitHub Actions:
            - CI: Pytest for unit tests, Ruff for linting, integrated with pre-commit hooks.
            - CD: Keyless authentication (WIF) and deployment to GCP Artifact Registry.
            - Implemented DockerOperator for ML services and Airflow integration.
    - Tools:
        - PowerBI | Docker | Docker Compose | Airflow | Terraform | PostgreSQL | IAM | Workload Identity Federation | GCS | BigQuery | S3 | Redshift | Google Artifact Registry | Github Actions (CI/CD) | API OAuth 2.0 | RestAPI | Decision Tree | RFM | KMeans | Association Rule | XGBoost | LightGBM | Pre-commit | Ruff | Pytest
- 👍[**MLOps-ml-system**](https://github.com/patcha-ranat/MLOps-ml-system)
    - This repository contains multiple sub-projects related to MLOps practices (or data science and data engineering as required)
    - [MBTI-IPIP](https://github.com/patcha-ranat/MLOps-ml-system/blob/main/mbti_ipip/README.md)
        - This sub-project emphasizes not only MLOps practices but also data science methodology. It covers initiating a problem, applying ML to address it, and wrangling and labeling data to meet specific requirements. While MLOps practices, particularly ML model deployment, remain essential for continuously delivering a functional web service, this is achieved using Docker containers, Streamlit, and Azure Web App Service.
            - Leveraged semi-supervised learning to utilize simple Machine Learning algorithms effectively.
            - Developed a containerized ML application using Streamlit and Docker.
            - Provisioned Azure cloud resources for ML deployment using a Terraform remote backend.
            - Deployed the ML application on Azure via Azure Web App Service, Azure CLI, and a Terraform-integrated CI/CD pipeline.
        - Tools
            - KMeans | Logistic Regression | Docker | Streamlit | Blob Storage | Azure Cloud Web App Service | Terraform CI/CD with remote backend
    - *(In progress . . .)*

- 👍[**Local Airflow K8s Helm**](https://github.com/patcha-ranat/local-airflow-k8s-helm)
    - Deploying Airflow on k8s locally using minikube, helm chart, and sync dag with volume mount
- [de-pyspark-airflow](https://github.com/patcha-ranat/de-pyspark-airflow)
    - Data Ingestion of local parquet files to docker postgresDB using PySpark integrated with Airflow orchestrated by docker-compose.
        - Custom Airflow Operator written in OOP.
        - Extended official airflow docker image by installing pyspark and necessary dependencies (JAVA, JDBC jar file, and python package).
- [ML-Learning](https://github.com/patcha-ranat/ML-Learning)
    - Machine learning experiment for learning purpose.
    - Algorithm & ML development/evaluation research and note.
- [kde-zoomcamp](https://github.com/patcha-ranat/kde-zoomcamp)
    - Data Engineering Zoomcamp
        - Basics Docker/Docker Compose, Terraform, Airflow, dbt, Pyspark, Kafka
    - MLOps Zoomcamp
        - Mlflow, ML Deployment
    - Data Rockie Streamlit
- [TD-Test](https://github.com/patcha-ranat/TD-test)
    - ETL Pipeline with MongoDB, GCS, Bigquery, Docker, Airflow, and Terraform
- [Big-Data-for-Energy-Management](https://github.com/patcha-ranat/Big-Data-for-Energy-Management)
    - The project introduced understanding of the machine learning model development process, such as cross-validation, hyperparameter tuning, models' algorithm, mostly tree-based models, model evaluation and other techniques such as early stopping, imputation, data pre-processing, and feature engineering.
    - The energy demand inference from regression model can also be used further to cluster the similar energy consumption patterns which might be useful for us knowing the future energy consumption.

## Data Analysis Projects

- [Marketing-Dashboard](https://github.com/patcha-ranat/Marketing-Dashboard)
- [GrabSpark-Data-Analytics-for-Business-Use-Cases](https://github.com/patcha-ranat/GrabSpark-Data-Analytics-for-Business-Use-Cases)
- [food-retail-strategy](https://github.com/patcha-ranat/food-retail-strategy)
- [Online-Learning-Platform-Analysis](https://github.com/patcha-ranat/Online-Learning-Platform-Analysis)
- [Web-Scraping-and-Data-Analytics-PodBean](https://github.com/patcha-ranat/Web-Scraping-and-Data-Analytics-PodBean)
- [FB-Live-Analysis-Chadchart](https://github.com/patcha-ranat/FB-Live-Analysis-Chadchart)
- [Crime-REST-API-Machine-Learning](https://github.com/patcha-ranat/Crime-REST-API-Machine-Learning)
