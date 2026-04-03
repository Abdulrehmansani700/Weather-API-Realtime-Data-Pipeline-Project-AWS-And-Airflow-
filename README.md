# 🌦️ Real-time Weather Data Pipeline
Automated ETL Orchestration with Apache Airflow & AWS

#📌 Project Overview
This project implements a robust End-to-End Data Pipeline designed to ingest, transform, and store real-time weather metrics from global cities. Utilizing the OpenWeather API, the system automates the flow of data from source to a cloud-based data warehouse, enabling high-performance analytics.

# 🏗️ Architecture Design
Based on the architecture diagram, the pipeline follows a modern Medallion-style approach:
* Data Ingestion (Extraction): A Python-based extractor fetches raw JSON data from the OpenWeather API.
* Orchestration: Apache Airflow acts as the brain of the operation, managing task dependencies, retries, and scheduling via DAGs.
* Staging Layer (Amazon S3): Raw data is first persisted into an AWS S3 Bucket (Landing Zone) to ensure data durability.
* Transformation & Processing: Using Python and SQL, data is cleaned and structured.
* Storage Layer (PostgreSQL/RDS): Structured data is maintained in a relational database for intermediate processing.
* Data Warehousing (Amazon Redshift): The final, optimized dataset is loaded into AWS Redshift for BI (Business Intelligence) and analytical queries.

# 🛠️ Tech Stack
* Language: Python 3.9+
* Orchestration: Apache Airflow
* Cloud Infrastructure: AWS (S3, Redshift, EC2/MWAA)
* Database: PostgreSQL
* API: OpenWeatherMap API
* Environment: Docker (for Airflow deployment)

# 🚀 Key Features
* Fully Automated ETL: Zero manual intervention required once the DAG is triggered.
* Cloud-Native Scalability: Leverages AWS S3 for unlimited raw data storage and Redshift for massive parallel processing.
* Modular Codebase: Decoupled scripts for extraction, transformation, and loading (ETL).
* Logging & Monitoring: Integrated Airflow UI to monitor pipeline health and execution logs.

# ⚙️ Quick Start
`1. Prerequisites`
* AWS Account with S3 and Redshift access.
* OpenWeather API Key.
* Docker & Docker Compose installed.
 `2. Installation`
 `3. Running with Airflow`
Access the Airflow UI at localhost:8080 to trigger the weather_etl_dag.

# 📊 Data Schema Highlights
* Dimensions: City, Country, Latitude, Longitude.
* Metrics: Temp (Celsius), Feels Like, Humidity, Wind Speed, Weather Description.
* Timestamps: Record creation time and API data calculation time.

# 🤝 Future Enhancements
`Integrating Apache Kafka for streaming data ingestion.
Using dbt (Data Build Tool) for advanced transformations inside Redshift.
Visualizing data using Amazon QuickSight or Tableau.`
