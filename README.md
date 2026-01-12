# 🌦️ Airflow ETL Weather Pipeline

Welcome to **Airflow ETL Weather** — an end-to-end **ETL (Extract, Transform, Load) pipeline** built using **Apache Airflow** and **Astronomer Runtime**, fully containerized with **Docker**.

This project demonstrates how to design, run, and monitor a **production-style Airflow workflow** locally using the **Astronomer CLI**.

---

## 🚀 Overview

This project was generated using:

```bash
astro dev init


🧱 Project Structure
Airflow-ETLWeather/
├── dags/
│   ├── example_astronauts.py     # Example ETL DAG (Astronauts API)
│   └── etlweather.py             # Weather ETL DAG (custom)
├── include/                      # Additional files (optional)
├── plugins/                      # Custom Airflow plugins
├── tests/                        # DAG tests
├── Dockerfile                    # Astronomer Runtime image
├── airflow_settings.yaml         # Local Airflow configs (connections, vars)
├── packages.txt                  # OS-level dependencies
├── requirements.txt              # Python dependencies
└── README.md
