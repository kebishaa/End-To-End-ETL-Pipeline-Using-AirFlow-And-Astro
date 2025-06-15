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

![DAG](https://github.com/kebishaa/End-To-End-ETL-Pipeline-Using-AirFlow-And-Astro/blob/main/images/photo_2025-06-13_12-55-49.jpg?raw=true)
 # Tasks:

● extract_weather_data: Connects to the Open-Meteo API using Airflow’s HttpHook and retrieves current weather data.

● transform_weather_data: Extracts relevant fields such as temperature, windspeed, and weather code from the JSON response.

● load_weather_data: Creates a weather_data table (if not exists) and inserts the transformed data into PostgreSQL using PostgresHook.

🛠️ Getting Started
# 1. Clone the Repository
        ```bash
     git clone https://github.com/kebishaa/End-To-End-ETL-Pipeline-Using-AirFlow-And-Astro.git
  cd End-To-End-ETL-Pipeline-Using-AirFlow-And-Astro

# 2. Install Astro CLI (if not installed)
Follow Astro CLI installation from: https://docs.astronomer.io/astro/install-cli
# 3. Start the Airflow Project
     ```bash
     astro dev start
# 4. Access the Airflow UI
Visit http://localhost:8080

Login with:

Username: admin

Password: admin
# 5. Setup Airflow Connections
In Airflow UI → Admin → Connections:
Connection ID: open_meteo_api

Type: HTTP

Host: https://api.open-meteo.com

Connection ID: postgres_default

Type: Postgres

Host: postgres

Schema, Login, Password should match your Docker Postgres config.

