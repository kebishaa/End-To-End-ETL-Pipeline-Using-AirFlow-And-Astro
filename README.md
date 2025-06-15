# 🌤️ End-to-End ETL Pipeline Using Apache Airflow and Astro
This project demonstrates a complete ETL (Extract, Transform, Load) pipeline built using Apache Airflow and Astro CLI, designed to extract current weather data from the Open-Meteo API, transform it, and load it into a PostgreSQL database.

# 🚀 Project Overview
The pipeline consists of three main steps:

● Extract: Fetches real-time weather data for London using the Open-Meteo API.

● Transform: Processes and cleans the raw data to a structured format.

● Load: Inserts the processed data into a PostgreSQL database for storage and future analysis.


This ETL pipeline is scheduled to run daily using Airflow’s scheduling system.

# 📦 Technologies Used
● Apache Airflow 3.0+

● Astro CLI (from Astronomer)

● Python

● PostgreSQL

● Open-Meteo API

● Docker (via Astro for environment management)

# 🗂️ DAG Structure
```bash
dag_id='weather_etl_pipeline'
schedule='@daily'
catchup=False
