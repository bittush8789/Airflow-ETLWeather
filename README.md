# 🌦️ Airflow ETL Weather Pipeline

Welcome to **Airflow ETL Weather** — an end-to-end **ETL (Extract, Transform, Load) pipeline** built using **Apache Airflow** and **Astronomer Runtime**, fully containerized with **Docker**.

This project demonstrates how to design, run, and monitor a **production-style Airflow workflow** locally using the **Astronomer CLI**.

---

## 🚀 Overview

This project was generated using:

```bash
astro dev init
It showcases:

Local Airflow development using Astronomer Runtime

DAG-based ETL orchestration

Dockerized execution environment

PostgreSQL as the Airflow metadata database

The pipeline can be easily extended to fetch weather data from APIs, transform it, and load it into downstream systems.

🧱 Project Structure
text
Copy code
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
🧩 Example DAG: example_astronauts
The example_astronauts DAG demonstrates:

A simple ETL pipeline

Fetching data from the Open Notify API

Using the TaskFlow API

Dynamic task mapping to process multiple astronauts dynamically

This DAG is a great reference for building scalable Airflow pipelines.

📘 Learn more:
https://www.astronomer.io/docs/learn/get-started-with-airflow

⚙️ Prerequisites
Make sure you have the following installed:

Docker Desktop (v20+)

Docker Compose

Git

Astronomer CLI

🧑‍🚀 Install Astronomer CLI
macOS / Linux
bash
Copy code
curl -sSL install.astronomer.io | sudo bash
Windows (PowerShell)
powershell
Copy code
winget install -e --id Astronomer.Astro
Verify Installation
bash
Copy code
astro version
▶️ Run Airflow Locally
1️⃣ Clone the Repository
bash
Copy code
git clone https://github.com/bittush8789/Airflow-ETLWeather.git
cd Airflow-ETLWeather
2️⃣ Start Airflow
bash
Copy code
astro dev start
This command spins up 4 Docker containers:

Container	Purpose
Postgres	Airflow Metadata Database
Webserver	Airflow UI
Scheduler	Task scheduling & execution
Triggerer	Deferred task handling

Verify running containers:

bash
Copy code
docker ps
🌐 Access Airflow UI
Open your browser and go to:

arduino
Copy code
http://localhost:8080
Login Credentials
Username: admin

Password: admin

🗄️ Database Access
PostgreSQL is exposed at:

bash
Copy code
localhost:5432/postgres
Access PostgreSQL via Docker:

bash
Copy code
docker exec -it airflow-etlweather_postgres_1 psql -U postgres
🔐 Airflow Configuration
Use airflow_settings.yaml to define:

Connections

Variables

Pools

This avoids manual configuration through the Airflow UI during local development.

🧪 Testing DAGs
Run DAG tests using:

bash
Copy code
pytest
This helps catch:

Import errors

DAG definition issues

Broken dependencies

🛠️ Common Troubleshooting
🚫 Port Already in Use
bash
Copy code
lsof -ti:8080 | xargs kill -9
lsof -ti:5432 | xargs kill -9
❌ DAG Not Showing in UI
bash
Copy code
astro dev restart
❌ Containers Failing to Start
bash
Copy code
docker system prune -a
astro dev start
🚢 Deploy to Astronomer (Cloud)
If you have an Astronomer account, you can deploy this project easily.

📘 Deployment Guide:
https://www.astronomer.io/docs/astro/deploy-code/

🎯 Learning Outcomes
By working on this project, you gain hands-on experience with:

Apache Airflow DAG development

Astronomer Runtime

Dockerized data pipelines

TaskFlow API & dynamic task mapping

Workflow monitoring & debugging

📌 Use Cases
Data Engineering portfolio project

Airflow interview preparation

Foundation for production ETL pipelines

MLOps & DevOps workflow orchestration practice

🤝 Support & Community
The Astronomer CLI is maintained by the Astronomer Team.

📖 Docs: https://www.astronomer.io/docs/

🐞 Issues & Support: https://www.astronomer.io/support/

